# S3
random s3 stuff

To s3 from local
i) aws s3 cp ‘Project/’run file’ s3://XXX/’Project’  --recursive
Move from s3
Aws s3 cp s3://XXX ./ --recursive --exclude '*' --include '*fastqc.html'    
Optional --dryrn


Login to EC2 , ubuntu lts
ssh -i surfer.pem -v  -L XXX.ca-central-1.compute.amazonaws.com

Add -N for only VNC version 

Use sync instead of cp (no --recursive needed) to copy only differences to destination (will not delete in dest)


aws s3 sync  ./ s3://XXX/

Multiqc run
Get files from s3
aws s3 cp s3://XXX/ ./  --profile user1 --recursive --exclude "*" --include "*fastqc.html"

Run 
multqc . 


Get featurecountssummaryfile
Do this for each study 
aws s3 sync s3://XXX/ ./UCSDfcs  --exclude "*" --include "*feature_summaryCounts.txt" --profile user1
find -name "*feature_summaryCounts*" -exec cp {} ./fcs/ \;


