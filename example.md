---
theme: ./
---

# Vue 3 + Supabase

<p class="!opacity-50">
The Open Source
Firebase Alternative
</p>

Zernonia (@zernonia)

<div class="pt-12">
  <button @click="next" class="px-6 py-3 bg-green-500 hover:!bg-green-600 rounded-md cursor-pointer hover:bg-white hover:bg-opacity-10">
    Let's go! <carbon:arrow-right class="inline"/>
  </button>
</div>

---
layout: cover
---

<div class="flex space-x-20 items-center">
<img class="w-60 h-60 rounded-full object-cover border-8 border-green-500 " src="https://www.zernonia.com/_vercel/image?url=/avatar.jpg&w=1024&q=80">
<div>

# Zernonia

A simple Vue developer, but **Supabase enthusiast!** <br>
Creator of [Made With Supabase](https://madewithsupabase.com), and some community projects

<div class="flex space-x-2 mt-12 mb-2">
<mdi-github class="w-6 h-6" /> 
<mdi-twitter class="w-6 h-6" /> 
<mdi-account class="w-6 h-6" /> 
</div>
<a href="https://zernonia.com">@ zernonia</a>

</div>
</div>

---
layout: center
---

<div class="flex items-center">
<Supabase class="w-12 h-12 mb-6 mr-4 !w-full" />

# Supabase
</div>


---
layout: center
---


<div class="flex items-center w-full ">
<Supabase class="w-12 h-12 mb-6 mr-4 " />

# Supabase
</div>

Supabase is an open source **Firebase alternative**.

It provides all the backend services you need to build a product. <br>
You can use it completely, or just the services you require:

<div class="grid grid-cols-2 gap-y-4 mt-12"> 
  <div class="flex items-center">
    <div class="text-black bg-white p-2 w-max rounded-lg mr-4 ">
      <mdi-database-outline class="w-6 h-6" />
    </div> 
      Database
  </div>

  <div class="flex items-center">
    <div class="text-black bg-white p-2 w-max rounded-lg mr-4 ">
      <mdi-key-outline class="w-6 h-6" />
    </div> 
      Authentication
  </div>

  <div class="flex items-center">
    <div class="text-black bg-white p-2 w-max rounded-lg mr-4 ">
      <mdi-archive-outline class="w-6 h-6" />
    </div> 
      Storage
  </div>

  <div class="flex items-center text-gray-400">
    <div class="text-black bg-white p-2 w-max rounded-lg mr-4 ">
      <mdi-console class="w-6 h-6" />
    </div> 
      Function
  </div>
</div>


<br>

<!-- Database -->
---

<div class="flex items-center">
  <div class="text-black bg-white p-2 w-max rounded-lg mr-4 mb-4">
    <mdi-database-outline class="w-6 h-6" />
  </div> 

# Database
    
</div>

Supabase is built on top of Postgres, an extremely scalable Relational Database.

<img class="" src="https://supabase.io/images/blog/pg13/postgres-13-og.jpg" >

---
layout: center
---

![meme](https://www.meme-arsenal.com/memes/93d97c676718b249359cff283560ce46.jpg)

---

<div class="flex items-center">
  <div class="text-black bg-white p-2 w-max rounded-lg mr-4 mb-4">
    <mdi-database-outline class="w-6 h-6" />
  </div> 

# Database
    
</div>

<div class="grid grid-cols-2 gap-x-4 gap-y-2">

<div>

### Read 

```javascript
const { data, error } = await supabase
  .from<City>('cities')
  .select('name')
```
</div>

<div>

### Create

```javascript
const { data, error } = await supabase
  .from<City>('cities')
  .insert([
    { name: 'The Shire', country_id: 554 },
    { name: 'Rohan', country_id: 555 },
  ])
```
</div>

```javascript
const { data, error } = await supabase
  .from<City>('cities')
  .update({ name: 'Middle Earth' })
  .match({ name: 'Auckland' })
```

```javascript
const { data, error } = await supabase
  .from('cities')
  .delete()
  .match({ id: 666 })
```


</div>

[Database.dev](https://database.dev)

---
<!-- Auth -->
---

<div class="flex items-center">
   <div class="text-black bg-white p-2 w-max rounded-lg mb-4 mr-4 ">
      <mdi-key-outline class="w-6 h-6" />
    </div> 

# Authentication
    
</div>

Supabase makes it simple to manage your users. <br>
Add user sign ups and logins, securing your data with Row Level Security.

<img class="w-116" src="https://supabase.io/_next/image?url=%2Fimages%2Fproduct%2Fauth%2Fheader--dark.png&w=1920&q=75" >

<img class="w-116" src="https://pbs.twimg.com/media/FCFJhQ4WYAMqDAM?format=jpg&name=medium" >


<!-- Storage -->
---

<div class="flex items-center">
   <div class="text-black bg-white p-2 w-max rounded-lg mb-4 mr-4 ">
      <mdi-archive-outline class="w-6 h-6" />
    </div> 

# Storage
    
</div>

Supabase Storage makes it simple to store and serve large files. <br>
Any media, including videos and images.


<img class="w-116" src="https://supabase.io/_next/image?url=%2Fimages%2Fproduct%2Fstorage%2Fheader--dark.png&w=1920&q=75" >

<img class="w-116" src="https://pbs.twimg.com/media/FCFJhQ4WYAMqDAM?format=jpg&name=medium" >


<!-- Function -->
---

<div class="flex items-center">
   <div class="text-black bg-white p-2 w-max rounded-lg mb-4 mr-4 ">
       <mdi-console class="w-6 h-6" />
    </div> 

# Function
    
</div>

Supabase Functions allow developers to write custom code <br>
and even cron jobs without deploying or scaling servers.

`coming soon`

---


---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel

### Keyboard Shortcuts

|                                                      |                             |
| ---------------------------------------------------- | --------------------------- |
| <kbd>space</kbd> / <kbd>tab</kbd> / <kbd>right</kbd> | next animation or slide     |
| <kbd>left</kbd> / <kbd>shift</kbd><kbd>space</kbd>   | previous animation or slide |
| <kbd>up</kbd>                                        | previous slide              |
| <kbd>down</kbd>                                      | next slide                  |

---

layout: image-right
image: 'https://source.unsplash.com/collection/94734566/1920x1080'

---

# Code

Use code snippets and get the highlighting directly!

```ts
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

---

layout: center
class: "text-center"

---

# Learn More

[Documentations](https://sli.dev) / [GitHub Repo](https://github.com/slidevjs/slidev)
