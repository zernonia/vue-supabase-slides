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

<div class="grid grid-cols-2 place-items-center h-full">
  <div class="flex flex-col justify-center">
    <div class="flex items-center">
      <div class="text-black bg-white p-2 w-max rounded-lg mr-4 mb-4">
        <mdi-database-outline class="w-6 h-6" />
      </div> 
    </div>

  # Database

  Supabase is built on top of Postgres, an extremely scalable **Relational Database**.
  </div>

  <div class="w-full h-full flex items-center">
  <img class="object-fits"  src="https://supabase.io/_next/image?url=%2Fimages%2Fproduct%2Fdatabase%2Fheader--dark-2.png&w=3840&q=75" >
  </div>

</div>

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


  _
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


<div>

### Update

```javascript
const { data, error } = await supabase
  .from<City>('cities')
  .update({ name: 'Middle Earth' })
  .match({ name: 'Auckland' })
```
</div>


<div>

### Delete 

```javascript
const { data, error } = await supabase
  .from<City>('cities')
  .delete()
  .match({ id: 666 })
```
</div>


</div>

---

### Even more powerful...

Create postgres function:
```sql
create or replace function get_tags (tag text)  -- params: tag
returns setof product
language plpgsql
as $$
begin
  return query 
    select * from product where tag % any(categories);
end; $$ 
```

Invoke postgres function using Supabase
```javascript
const { data, error, count } = await supabase
  .rpc(
    "get_tags",
    { tag: 'Macbook' }  // pass data into parameter
  )
```

<!-- Auth -->
---

<div class="grid grid-cols-2 place-items-center h-full">
  <div class="flex flex-col justify-center">
    <div class="flex items-center">
      <div class="text-black bg-white p-2 w-max rounded-lg mb-4 mr-4 ">
        <mdi-key-outline class="w-6 h-6" />
      </div> 
    </div>

  # Authentication
        
  Supabase makes it simple to manage your users. <br>
  Add user sign ups and logins, securing your data <br> with **Row Level Security**.
  

  </div>

  

  <div class="w-full h-full flex items-center">
  <img class="object-fits"  src="https://pbs.twimg.com/media/FCFJhQ4WYAMqDAM?format=jpg&name=medium" >
  </div>

</div>

---
layout: image
image: assets/images/auth.png

---

---

<div class="grid grid-cols gap-x-4 gap-y-2">

<div>

## Sign Up/Sign In

### using Email

```javascript
const { user, session, error } = await supabase.auth.signUp({
  email: 'example@email.com',
  password: 'example-password',
})

const { user, session, error } = await supabase.auth.signIn({
  email: 'example@email.com',
  password: 'example-password',
})
```
</div>

<div>

### using Social login

```javascript
async function signInWithGoogle() {
  const { user, session, error } = await supabase.auth.signIn({
    provider: 'google'  // 'github', 'apple', 'twilio', etc...
  });
}
```
</div>

</div>

---

## Security Rules

Supabase utilize Postgres' super granular **Row Level Security**, where user can create policy on each table that restrict the CRUD operations.

```sql
-- 1. Enable RLS
alter table profiles
  enable row level security;

-- 2. Create Policy
create policy "Public profiles are viewable by everyone."
  on profiles for select using (
    true
  );

-- 3. Create Policy
create policy "Users can update their own profiles."
  on profiles for update using (
    auth.uid() = id  
    -- `auth.uid()`, `auth.role()`, `auth.email()` are predefined helper functions
  );
```


<!-- Storage -->
---

<div class="grid grid-cols-2 place-items-center h-full">
  <div class="flex flex-col justify-center">
    <div class="flex items-center">
      <div class="text-black bg-white p-2 w-max rounded-lg mb-4 mr-4 ">
        <mdi-archive-outline class="w-6 h-6" />
      </div> 
    </div>

  # Storage
        
  Supabase Storage makes it simple to store <br> and serve large files. **Any media**, <br> including videos and images.

  </div>

  

  <div class="w-full h-full flex items-center">
  <img class="object-fits"  src="https://supabase.io/_next/image?url=%2Fimages%2Fproduct%2Fstorage%2Fheader--dark.png&w=1920&q=75">
  </div>

</div>


<!-- Function -->
---

<div class="grid grid-cols-2 place-items-center h-full">
  <div class="flex flex-col justify-center">
    <div class="flex items-center">
      <div class="text-black bg-white p-2 w-max rounded-lg mb-4 mr-4 ">
        <mdi-console class="w-6 h-6" />
      </div> 
    </div>

  # Function
        
  Write custom code and even cron jobs without <br> deploying or scaling servers.

`coming soon`

  </div>

  

  <div class="w-full h-full flex items-center">
  <img class="object-fits"  src="https://supabase.io/images/blog/functions-updates/thumb-supabase-hooks.jpg">
  </div>

</div>

---
layout: center
---

# Let's code! 🧑🏻‍💻

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
