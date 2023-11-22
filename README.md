# Balance Buddy

Testing a simple ReactJS application using Jest and Enzyme.

# Study Insights

This project was significantly inspired by and developed with insights gained from the video tutorial ["React testing with Jest and Enzyme"](https://www.youtube.com/watch?v=XNzVMP7Mnxg&ab_channel=Duomly) by Duomly. 

The decision to follow this particular tutorial was driven by its clear, concise explanations and practical examples.

## Important

This project was developed using React 16 and requires Node.js version 16. If you are using a different version of Node.js, particularly any version higher than 16, you may encounter errors. 

## Node.js Version Compatibility Error

The error error:0308010C:digital envelope routines::unsupported is frequently encountered by developers working with Node.js, particularly when using versions higher than 16. This issue arises due to changes in how Node.js manages cryptography, a shift primarily driven by the adoption of OpenSSL's new cryptographic module policy.

With the release of Node.js version 17, OpenSSL has been set to use the "default" implementation provider, moving away from the "legacy" option. This transition can create challenges in systems that have not been updated to support the most recent standards. This modification is part of a broader initiative to modernize and bolster security within the Node.js environment. However, it necessitates that developers proactively update their systems and codebases. Doing so ensures continued compatibility and allows them to benefit from the latest improvements in cryptographic technology.

```javascript
  Error: error:0308010C:digital envelope routines::unsupported
      at new Hash (node:internal/crypto/hash:69:19)
      at Object.createHash (node:crypto:133:10)
      at module.exports (your\path\balance-buddy\node_modules\webpack\lib\util\createHash.js:135:53)
      at NormalModule._initBuildHash (your\path\balance-buddy\node_modules\webpack\lib\NormalModule.js:417:16)
      at your\path\balance-buddy\node_modules\webpack\lib\NormalModule.js:452:10
      at your\path\balance-buddy\node_modules\webpack\lib    at your\path\balance-buddy\node_modules\loader-runner\lib\LoaderRunner.js:367:11
      at your\path\balance-buddy\node_modules\loader-runner\lib\LoaderRunner.js:233:18
      at context.callback (your\path\balance-buddy\node_modules\loader-runner\lib\LoaderRunner.js:111:13)
      at your\path\balance-buddy\node_modules\babel-loader\lib\index.js:59:103 {
    opensslErrorStack: [ 'error:03000086:digital envelope routines::initialization error' ],    
    library: 'digital envelope routines',
    reason: 'unsupported',
    code: 'ERR_OSSL_EVP_UNSUPPORTED'
  }
```
#### How To Fix

To resolve this error, you have several options to consider.

Opiton 1:

1. Downgrade to Node.js v16.
2. Enable legacy OpenSSL provider.
   - On Unix-like (Linux, macOS, Git bash, etc.):
   `export NODE_OPTIONS=--openssl-legacy-provider`
   - On Windows command prompt:
   `set NODE_OPTIONS=--openssl-legacy-provider`
3. In your package.json: change this line.
`"start": "react-scripts start"`
to
`"start": "react-scripts --openssl-legacy-provider start"`

Option 2:

To Windows users: 

Install Manage Multiple Installations of Node.js on a Windows Computer

1. Visit [nvm-windows](https://github.com/coreybutler/nvm-windows) and download the nvm-windows installer.
2. Open your command prompt.
3. Install Node.js 16 version:
`nvm install 16`
1. Switch to use Node.js 16 version:
`nvm use 16`
1. Check all installed Node.js versions:
`nvm list`

See more: https://github.com/coreybutler/nvm-windows

Option 2:

Another way to fix the issue is to run `npm audit fix --force` after executing `npm install`.

## Getting Started

For Node.js version 16 or below:

```
  npm i
  npm start
```

For Node.js version greater than 16:

```
  npm i
  npm audit fix --force
```

## Tecnologies

[Enzyme](https://enzymejs.github.io/enzyme/)
[Jest](https://jestjs.io/)
[React.js](https://react.dev/)
