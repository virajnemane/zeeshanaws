split -b 300MB --verbose 1GB.bin

aws s3api create-multipart-upload --bucket testbucket3199 --key largefile

ubuntu@ip-10-21-150-242:/tmp/upload$ aws s3api create-multipart-upload --bucket testbucket3199 --key largefilenew
{
    "AbortDate": "Mon, 07 Mar 2022 00:00:00 GMT",
    "AbortRuleId": "abc",
    "Bucket": "testbucket3199",
    "Key": "largefilenew",
    "UploadId": "nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_"
}


aws s3api upload-part --bucket testbucket3199 --key largefilenew --part-number 1 --body xaa --upload-id nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_
aws s3api upload-part --bucket testbucket3199 --key largefilenew --part-number 2 --body xab --upload-id nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_
aws s3api upload-part --bucket testbucket3199 --key largefilenew --part-number 3 --body xac --upload-id nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_
aws s3api upload-part --bucket testbucket3199 --key largefilenew --part-number 4 --body xad --upload-id nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_


aws s3api list-parts --bucket testbucket3199 --key largefilenew --upload-id nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_


aws s3api complete-multipart-upload --multipart-upload file://fileparts.json --bucket testbucket3199 --key largefilenew --upload-id nl7e1WNm5EMoGzMpdyBSPygBJKh5pg8XSAP2ih4hStqM9hx4PkbGphH_7trau7K3f.v8PQuZyElX9A0jIGzXTlWwiozIDpAOT6Xa2Wnfh2sQM1OVvlGY1kA8hEK8ldH_


----

{
    "Parts": [{
        "ETag": "4baf99888b333a7330f5c97c17e5a9df",
        "PartNumber":1
    },
    {
        "ETag": "4baf99888b333a7330f5c97c17e5a9df",
        "PartNumber":2
    },
{
        "ETag": "4baf99888b333a7330f5c97c17e5a9df",
        "PartNumber":3
    },
    {
        "ETag": "81e3adf66401f08364e1bc66ed7312ed",
        "PartNumber":4
    }]
}
