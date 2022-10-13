 # 1. Environment variables in production
 There are different solution to the problem depending upon the platform and the environment you are using.

1. Online platform like vercel, netlify, github.
	1. These service provider provides their own way of storing the environment variables and we can use them directly
	2. These service also provide Secret keys that can be used to decrypt environment variables stored within the app it self.
2. Encryption.
	1. Encrypt your environment variable with public and private encryption key. Give public key to Developer 