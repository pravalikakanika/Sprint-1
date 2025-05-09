# Install AWS SDK (for Node.js Example)

Create a new project folder and run:

```bash
npm init -y
npm install aws-sdk
```

# Simple Notification Script (Node.js)

## Steps to Create the Script

1. Create a file named `sendNotification.js`.

2. Set up the SNS notification sending logic in the file:

```javascript
const AWS = require('aws-sdk');

// Set the region 
AWS.config.update({ region: 'us-east-1' });

const sns = new AWS.SNS();

// Define your SNS topic ARN (replace with your own Topic ARN)
const topicArn = 'arn:aws:sns:us-east-1:123456789012:NotificationPOC';

// Create a publish params object
const params = {
  Message: 'Hello, this is a test notification from the POC app!',
  TopicArn: topicArn,
};

// Publish to the SNS topic
sns.publish(params, function (err, data) {
  if (err) {
    console.log('Error sending notification:', err);
  } else {
    console.log('Notification sent:', data);
  }
});
```

# Test the Notification Script

Run the script using Node.js:

```bash
node sendNotification.js
```
