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

  <div class="flex items-center opacity-50">
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
  .from<Product>('products')
  .select('name')


  _
```
</div>

<div>

### Create

```javascript
const { data, error } = await supabase
  .from<Product>('products')
  .insert([
    { name: 'Cool Swag', tag: ['swag', 'black'] },
    { name: 'Stickers', tag: ['swag', 'sticker'] },
  ])
```
</div>


<div>

### Update

```javascript
const { data, error } = await supabase
  .from<Product>('products')
  .update({ name: 'New Swag' })
  .match({ name: 'Cool Swag' })
```
</div>


<div>

### Delete 

```javascript
const { data, error } = await supabase
  .from<Product>('products')
  .delete()
  .match({ name: 'Cool Swag' })
```
</div>


</div>

---
layout: center
---

<img src="https://media.giphy.com/media/3o7btNa0RUYa5E7iiQ/giphy.gif">

---

## Even more powerful...

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
    { tag: 'swag' }  // pass data into parameter
  )
```

---

## Also, Realtime Subscription
Subscribe to realtime changes in your database.

```javascript
const mySubscription = supabase
  .from('products')
  .on('UPDATE', payload => {
    console.log('Change received!', payload)
    // do something
  })
  .subscribe()
```

<img src='https://media.giphy.com/media/L4Bb7zCaP8FB5C769T/giphy.gif' style="margin-top: 2rem;" >

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
layout: image
image: /images/auth.png
---

---
layout: center
---

<img class="w-128 mt-20 rounded-lg" src="/images/supabase-auth.png">

---
layout: center
---

<img src="https://media.giphy.com/media/SACoDGYTvVNhZYNb5a/giphy.gif">

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

---

## Storage

Bucket based storage. You can create distinct buckets for different Security and Access Rules.

For example, you might keep all public files in a "public" bucket, and other files that require logged-in access in a "restricted" bucket.

<div class="grid grid-cols-2 gap-x-4 gap-y-2">

```javascript
const imageFile = event.target.files[0]
const { data, error } = await supabase
  .storage
  .from('products')
  .upload('public/swag.png', imageFile)
```

```javascript
const imageFile = event.target.files[0]
const { data, error } = await supabase
  .storage
  .from('products')
  .upload('secret/swag/shhhh.png', imageFile)
```

</div>


<div class="grid grid-cols-1 gap-y-4 mt-12"> 
  
  `coming soon`

  <div class="flex items-center  opacity-50">
    <div class="text-black bg-white p-2 w-max rounded-lg mr-4 ">
      <mdi-wifi class="w-6 h-6" />
    </div> 
      CDN
  </div>

  <div class="flex items-center opacity-50">
    <div class="text-black bg-white p-2 w-max rounded-lg mr-4 ">
      <ph:magic-wand-fill  class="w-6 h-6" />
    </div> 
      Transformation
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

# Let's see some 
# **Vue 3 + Supabase** in action!

<a target='blank' href="https://supabase-realtime-playground.vercel.app">supabase-realtime-playground.vercel.app</a>

---

## Fetch button's count

`src/components/PlayButton.vue`
```javascript
const fetchData = async () => {
  const { data } = await supabase.from("realtime_playbutton").select("*")
}
```

<div class="my-12" ></div>


## Listen to Realtime


`src/components/PlayButton.vue`
```javascript
const listen = () =>
  supabase
    .from("realtime_playbutton")
    .on("UPDATE", (payload) => {
      const { count, name } = payload.new
      // do something 
    })
    .subscribe()
```

---

## Login with Twitter

`src/components/ModalLogin.vue`
```javascript
const loginTwitter = async () => {
  const { user, session, error } = await supabase.auth.signIn({
    provider: "twitter",
  })
}
```

<div class="my-12" ></div>

`src/App.vue`
```javascript
supabase.auth.onAuthStateChange(async (ev, session) => {
  if (ev == "SIGNED_IN") {
    // do stuff when user sign in, or session is not expired
  }
})
```

---
layout: center
---

# It's just that simple!

---
layout: center
---

# So... what's so different about **Supabase**?
# It's the..

---

# It's the fun!

![Supabase Hacktoberfest](https://supabase.io/images/blog/hacktoberfest-hackathon/hacktoberfest_banner.png)

---

# It's the swag!

![Supabase Swag](https://supabase.io/images/blog/swag-store/cover-swag-store.jpg)

---

# It's the meme!

![Supabase Meme](https://pbs.twimg.com/media/FC16hl9aQAAV1Tb?format=jpg&name=medium)

---

# It's the people!

![Supabase Meme](https://pbs.twimg.com/media/FAoCLHkVIAcMnP2?format=jpg&name=4096x4096)

---
layout: center
---

# Join us now!