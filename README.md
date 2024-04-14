# Rbar
# Bar plots in R for visualizing student achievement data
# For summative achievement test results in four performance levels, this R code will create stacked bar charts in which the horizontal axis is at the level of proficiency.

colvec<-c("green","blue","red4","red1","white")
levlab<-c("Exceeded","Met","Nearly Met", "Not Met", "")

stagstack<-function(data,id,value,variable,lab,colvec,levlab){
  g<-ggplot(data,aes(x=id,y=value,fill=variable,label=lab))+
    geom_bar(stat="identity")+
    scale_fill_manual(values = colvec,
                      name = "Levels",
                      labels = levlab)+
    geom_text(size=3,position=position_stack(vjust=0.5),col="white")
}
