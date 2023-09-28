**README.md**

**Tips**

* **Change host value**

If you want to deploy your Node.js app to a production server, you need to change the host value from `localhost` to `0.0.0.0`. This will allow your app to be accessible from the internet.

```
host: 'localhost' -> host: process.env.NODE_ENV !== 'production' ? 'localhost' : '0.0.0.0',
```

* **Add runner script on package.json**

You can add a runner script to your `package.json` file to start your app in production mode. This will set the `NODE_ENV` environment variable to `production`.

```json
{
  "scripts": {
    "start-prod": "NODE_ENV=production node ./src/server.js"
  }
}
```

* **Use process manager**

A process manager can help you to manage your Node.js app in production. It can automatically restart the app if it crashes, and it can also keep the app running in the background.

To use a process manager, you first need to install it. You can install PM2 globally with the following command:

```
~$ npm install -g pm2
```

Once PM2 is installed, you can start your Node.js app in production mode with the following command:

```
~$ pm2 start npm --name "notes-api" -- run "start-prod"
```

This will start your app in the background and keep it running even if your terminal session is closed.

You can also use PM2 to restart and stop your app. To restart the app, use the following command:

```
~$ pm2 restart notes-api
```

To stop the app, use the following command:

```
~$ pm2 stop notes-api
```

**Conclusion**

With these instructions and the power of PM2, you can ensure your Node.js application runs smoothly, even in production environments, while maintaining uptime and stability.
