---
cssclass: dashboard
---
# Todos
```tasks
not done
short mode
hide backlinks
```
# Vault Info
- 🗄️ Recent file updates
 `$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(4).file.link)`
- 🔖 Tagged:  favorite 
 `$=dv.list(dv.pages('#favorite').sort(f=>f.file.name,"desc").limit(4).file.link)`
- 〽️ Stats
	-  File Count: `$=dv.pages().length`
	-  Personal recipes: `$=dv.pages('"Family/Recipes"').length`
	- 


![](https://lh6.googleusercontent.com/bD_nte6D8RuwMCFBgMtM5us7oOADcOBzAarSwZ7KtLt8Z6jnxLaPKTYQudL2hkQfa4HaJUvVND21q-g0G6XiuGnybbO6FoypWAFaZj6awOOapa4b0_0OddecdMcsr5EvY--MqLDtsIyjCyzv1qxftPEJA76bVnlwHJzRY5cyQBd1xcKCqf6eKGrugEKwgQ)

