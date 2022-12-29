const k_mean_cluster=(array)=>{
if(array.length>1){
let x=y=0;
let plot1=new Array();
let plot2=new Array();
let centroid1=new Array();
let centroid2=new Array();
centroid1=array[0];
centroid2=array[1];
plot1=[centroid1];
plot2=[centroid2];
x+=1;
y+=1;
for(let i=2;i< array.length;i++){
let ed1=Math.sqrt((Math.pow(centroid1[0]-array[i][0],2))+ (Math.pow(centroid1[1]- array[i][1],2)));
let ed2=Math.sqrt((Math.pow(centroid2[0]-array[i][0],2))+(Math.pow(centroid2[1]- array[i][1])));
if(ed1>ed2){
centroid2[0]=(centroid2[0]+array[i][0])/2;
centroid2[1]=(centroid2[1]+array[i][1])/2;
if(plot2){
plot2=[...plot2,centroid2];
}
y+=1;
}
else{
centroid1[0]=(centroid1[0]+array[i][0])/2;
centroid1[1]=(centroid1[1]+array[i][1])/2;
if(plot1){
plot1=[...plot1,centroid1];
}
x+=1;
}
}
return {plot1,plot2}
}
else{
return {plot1:'Only Two Points are Acceptable and Array length should be more than 1',
plot2:'Only Two Points are Acceptable and Array length should be more than 1'
}
}
}
