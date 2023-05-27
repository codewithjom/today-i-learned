# NextJS CRUD using Prisma

## CREATE

```ts
import { redirect } from "next/navigation"

async function createData(data: FormData) {
  'use server'

  const post = data.get('post')?.valueOf()
  if (typeof post !== 'string' || post.length === 0)   {
    throw new Error('Invalid Post')
  }

  await prisma.data.create({ data: { post }})
  redirect('/')
}
```

```html
<form action={createData}>
  <div>
    <input type='text' name='post' />
    <button type='submit'>Send</button>
  </div>
</form>
```

## READ

```ts
import { prisma } from "@/prisma/client"

function readData() {
  return prisma.data.findMany()
}

export default async function Home() {

  const posts = await readData()

  return (
    <main>
      <ul>
        {posts.map(post => (
          <li key={post.id}>{post.post}</li>
        ))}
      </ul>
    </main>
  )
}
```
