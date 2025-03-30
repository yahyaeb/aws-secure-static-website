## 🌐 Check It Out

You can visit the live website here: [www.yahia-elboukili.com](https://www.yahia-elboukili.com)

----

## 🛠️ How I Built It

### Part 1: Host Static Site on S3
- Created a public S3 bucket
- Enabled static website hosting with `index.html`
- Uploaded the HTML file
- Added a bucket policy to allow public read access

### Part 2: Add HTTPS with CloudFront
- Created a CloudFront distribution
- Set origin as the S3 **website endpoint**
- Enabled `Redirect HTTP to HTTPS`
- Set `index.html` as the default root object

### Part 3: Register Domain via Route 53
- Purchased domain `yahia-elboukili.com`
- Enabled WHOIS privacy
- Added a Hosted Zone for DNS records

### Part 4: Get SSL Cert with ACM
- Switched to `us-east-1` region
- Requested certificate for `yahia-elboukili.com` and `*.yahia-elboukili.com`
- Validated via DNS (CNAME record auto-created in Route 53)

### Part 5: Link Domain to CloudFront
- Updated CloudFront to add `www.yahia-elboukili.com` as an alternate domain
- Attached SSL certificate from ACM
- Created an A-record in Route 53 pointing `www.yahia-elboukili.com` to the CloudFront distribution


---

## 💰 Cost Breakdown

| Service        | Cost         |
|----------------|--------------|
| S3             | Free Tier    |
| CloudFront     | Free Tier    |
| ACM (SSL)      | Free         |
| Route 53 DNS   | Free Tier    |
| Domain         | ~€12/year    |

---

## 🧠 Lessons Learned

- How to configure public S3 buckets securely
- How to set up DNS + SSL with AWS
- Region matters: ACM certs must be created in `us-east-1` for CloudFront
- CloudFront is powerful for global delivery + HTTPS termination

---

## 👨‍💻 Author

**Yahia Elboukili**
[GitHub](https://github.com/yahyaeb)

