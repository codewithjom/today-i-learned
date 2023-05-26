# Prisma in Nextjs

## Installation

``` sh
npm install -D prisma @prisma/client
```

## Initialize

This will create a folder **prisma** and inside the folder it will contain a file **schema.prisma**. It will also create a file **.env** in the root folder.

``` sh
npx prisma init
```

## Migrate

Once you are done creating a model inside the **schema.prisma** run the following:

``` sh
npx prisma migrate dev
```

## Studio

You can also use the **prisma studio**:

``` sh
npx prisma studio
```
