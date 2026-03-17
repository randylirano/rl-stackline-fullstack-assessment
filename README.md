# Stackline Full Stack Assignment

## Overview

This is a sample eCommerce website that includes:

- Product List Page
- Search Results Page
- Product Detail Page

The application contains various bugs including UX issues, design problems, functionality bugs, and potential security vulnerabilities.

## Getting Started

```bash
yarn install
yarn dev
```

## Your Task

1. **Identify and fix bugs** - Review the application thoroughly and fix any issues you find
2. **Document your work** - Create a comprehensive README that includes:
   - What bugs/issues you identified
   - How you fixed each issue
   - Why you chose your approach
   - Any improvements or enhancements you made

We recommend spending no more than 2 hours on this assignment. We are more interested in the quality of your work and your communication than the amount of time you spend or how many bugs you fix!

## Submission

- Fork this repository
- Make your fixes and improvements
- **Replace this README** with your own that clearly documents all changes and your reasoning
- Provide your Stackline contact with a link to a git repository where you have committed your changes

We're looking for clear communication about your problem-solving process as much as the technical fixes themselves.

# Discovered Issues

## 1. Search functionality crashed app

Description: Whenever searching through the text bar, eventually the app will crash with the following message:

```markdown
Invalid src prop (https://images-na.ssl-images-amazon.com/images/I/51FmiD0thfL.jpg) on next/image, hostname "images-na.ssl-images-amazon.com" is not configured under images in your next.config.js
See more info: https://nextjs.org/docs/messages/next-image-unconfigured-host
Next.js version: 15.5.4 (Turbopack)
```

Cause: Next.js's `<Image>` component blocks external image URLs by default as a security measure.

Fix: Added the missing `images-na.ssl-images-amazon.com` into the whitelist of allowed image source array in `next.config.js`.

## 2. Product being serialized into URL

Description: Opening any product details opens a product detail page with a very long URL route, example: [http://localhost:3000/product?product=%7B%22stacklineSku%22%3A%22PBYBN462D%22%2C%22featureBullets%22%3A%5B%22Transform+your+reality+and+do+everything+you+love+in+totally+new+ways.+Welcome+to+Meta+Quest+3S.+Now+you+can+get+the+Batman%3A+Arkham+Shadow*+and+a+3-month+trial+of+Meta+Horizon%2B\*\*%22%2C%22Explore+thousands+of+unreal+experiences+with+mixed+reality%2C+where+you+can+blend+digital+objects+into+the+room+around+you+or+dial+up+the+immersion+in+VR.%22%2C%22Have+more+fun+with+friends+in+Quest.+Whether+you%E2%80%99re+stepping+into+an+immersive+game+with+people+from+around+the+world%2C+watching+a+live+concert+together+in+Meta+Horizon+or+inviting+everyone+over+to+cast+your+play+onto+the+TV.%22%2C%22Multi-tasking+has+never+been+this+easy.+Pull+up+multiple+screens+at+once+to+browse+the+web%2C+watch+YouTube+and+direct+message+with+friends+%E2%80%94+all+while+keeping+your+room+in+view.%22%2C%22Turn+any+room+into+your+own+personal+theater.+Dim+the+space+around+you+and+watch+on+a+giant%2C+vibrant+screen.+Go+all+in+with+USB-C+headphones%2C+or+plug+in+any+3.5mm+headphones+with+a+USB-C+adapter+%28sold+separately%29.%22%2C%22Access+social+media+apps+like+WhatsApp%2C+Instagram+and+Facebook+Messenger+so+you+can+play+while+you+stay+in+the+group+chat.%22%2C%22Move+with+ultimate+wireless+freedom+and+lightweight+comfort+when+you+get+your+heart+pumping+in+virtual+workouts+or+use+your+whole+body+to+bust+ghosts+in+your+living+room.%22%2C%22Enjoy+powerful+performance+that+brings+virtual+objects+to+life+with+2X+the+graphical+processing+%28GPU%29+compared+to+Meta+Quest+2*.+Use+your+hands+to+swipe+through+content+or+your+Touch+Plus+Controllers+for+realistic+sensations+and+fine-tuned+precision.+\*Based+on+the+graphic+performance+of+the+Qualcomm+Snapdragon+XR2+Gen+2+platform+vs+the+Meta+Quest+2+platform.%22%2C%22Feel+safe+to+share+the+fun.+Manage+parental+controls%2C+check+your+child%E2%80%99s+daily+usage%2C+add+multiple+users%2C+share+content+and+set+permissions+for+everyone+in+the+family.+See+child+safety+guidance+online%3B+Accounts+for+10%2B.%22%5D%2C%22imageUrls%22%3A%5B%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F6144LWWqyWL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81TVBwtmMwL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F712qfZ%2B4YtL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81Zfe8eEY7L._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81GI%2Bp2mqkL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81aldh6oBTL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F815IrjXseRL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F61Gg6zKZARL._SL1500_.jpg%22%5D%2C%22subCategoryId%22%3A55785%2C%22title%22%3A%22Meta+Quest+3S+128GB+%E2%80%94+Get+Batman%3A+Arkham+Shadow+and+a+3-Month+Trial+of+Meta+Horizon%2B+Included+%E2%80%94+All-in-One+Headset%22%2C%22categoryName%22%3A%22Game+Consoles+%26+Accessories%22%2C%22retailPrice%22%3A299%2C%22retailerSku%22%3A%22B0DDK1WM9K%22%2C%22categoryId%22%3A1600%2C%22subCategoryName%22%3A%22Virtual+Reality+Gaming+%26+Accessories%22%7D](http://localhost:3000/product?product=%7B%22stacklineSku%22%3A%22PBYBN462D%22%2C%22featureBullets%22%3A%5B%22Transform+your+reality+and+do+everything+you+love+in+totally+new+ways.+Welcome+to+Meta+Quest+3S.+Now+you+can+get+the+Batman%3A+Arkham+Shadow*+and+a+3-month+trial+of+Meta+Horizon%2B**%22%2C%22Explore+thousands+of+unreal+experiences+with+mixed+reality%2C+where+you+can+blend+digital+objects+into+the+room+around+you+or+dial+up+the+immersion+in+VR.%22%2C%22Have+more+fun+with+friends+in+Quest.+Whether+you%E2%80%99re+stepping+into+an+immersive+game+with+people+from+around+the+world%2C+watching+a+live+concert+together+in+Meta+Horizon+or+inviting+everyone+over+to+cast+your+play+onto+the+TV.%22%2C%22Multi-tasking+has+never+been+this+easy.+Pull+up+multiple+screens+at+once+to+browse+the+web%2C+watch+YouTube+and+direct+message+with+friends+%E2%80%94+all+while+keeping+your+room+in+view.%22%2C%22Turn+any+room+into+your+own+personal+theater.+Dim+the+space+around+you+and+watch+on+a+giant%2C+vibrant+screen.+Go+all+in+with+USB-C+headphones%2C+or+plug+in+any+3.5mm+headphones+with+a+USB-C+adapter+%28sold+separately%29.%22%2C%22Access+social+media+apps+like+WhatsApp%2C+Instagram+and+Facebook+Messenger+so+you+can+play+while+you+stay+in+the+group+chat.%22%2C%22Move+with+ultimate+wireless+freedom+and+lightweight+comfort+when+you+get+your+heart+pumping+in+virtual+workouts+or+use+your+whole+body+to+bust+ghosts+in+your+living+room.%22%2C%22Enjoy+powerful+performance+that+brings+virtual+objects+to+life+with+2X+the+graphical+processing+%28GPU%29+compared+to+Meta+Quest+2*.+Use+your+hands+to+swipe+through+content+or+your+Touch+Plus+Controllers+for+realistic+sensations+and+fine-tuned+precision.+*Based+on+the+graphic+performance+of+the+Qualcomm+Snapdragon+XR2+Gen+2+platform+vs+the+Meta+Quest+2+platform.%22%2C%22Feel+safe+to+share+the+fun.+Manage+parental+controls%2C+check+your+child%E2%80%99s+daily+usage%2C+add+multiple+users%2C+share+content+and+set+permissions+for+everyone+in+the+family.+See+child+safety+guidance+online%3B+Accounts+for+10%2B.%22%5D%2C%22imageUrls%22%3A%5B%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F6144LWWqyWL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81TVBwtmMwL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F712qfZ%2B4YtL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81Zfe8eEY7L._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81GI%2Bp2mqkL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F81aldh6oBTL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F815IrjXseRL._SL1500_.jpg%22%2C%22https%3A%2F%2Fm.media-amazon.com%2Fimages%2FI%2F61Gg6zKZARL._SL1500_.jpg%22%5D%2C%22subCategoryId%22%3A55785%2C%22title%22%3A%22Meta+Quest+3S+128GB+%E2%80%94+Get+Batman%3A+Arkham+Shadow+and+a+3-Month+Trial+of+Meta+Horizon%2B+Included+%E2%80%94+All-in-One+Headset%22%2C%22categoryName%22%3A%22Game+Consoles+%26+Accessories%22%2C%22retailPrice%22%3A299%2C%22retailerSku%22%3A%22B0DDK1WM9K%22%2C%22categoryId%22%3A1600%2C%22subCategoryName%22%3A%22Virtual+Reality+Gaming+%26+Accessories%22%7D).

This is an issue because:

1. We are potentially exposing product information that should’ve been limited for certain audience.
2. There’s a limit to URL length

Cause:

The link reroute for each product, stringified the entire object

```tsx
<Link
  key={product.stacklineSku}
  href={`/product/${product.stacklineSku}`}
>
```

Fix:

Re-arrange the product detail page to `app/product/[id]/page.tsx` . Where id is the stack line SKU.

## 3. Missing pagination

Description:

- The response from `http://localhost:3000/api/products?limit=20&offset=0` indicates that we are showing the first 20 products out of the total of 500 products
- The main product listing page is missing any ability to show / query the remaining items

Fix:

- Added pagination concept to the product listing page

```tsx
<div className="flex items-center justify-between mb-4">
  <p className="text-sm text-muted-foreground">
    Showing {offset + 1}–{Math.min(offset + LIMIT, total)} of {total} products
  </p>

  <div className="flex gap-2">
    <Button
      variant="outline"
      size="sm"
      disabled={offset === 0}
      onClick={() => setOffset(offset - LIMIT)}
    >
      Previous
    </Button>
    <span className="text-sm text-muted-foreground py-2">
      Page {Math.floor(offset / LIMIT) + 1} of {Math.ceil(total / LIMIT)}
    </span>
    <Button
      variant="outline"
      size="sm"
      disabled={offset + LIMIT >= total}
      onClick={() => setOffset(offset + LIMIT)}
    >
      Next
    </Button>
  </div>
</div>
```

## 4. Search box calls API on every character

Description: When querying via search text, `http://localhost:3000/api/products?limit=20&offset=0` API being called with every typed character appended to the `search` parameter. This is a potential performance issue as we can flood our endpoint when we have a lot of user querying via search text.

Fix:

- Added a debounce search to the search functionality.
- Hold for 0.5 sec before querying products

## 5. Category and sub-category filters

Description

1. Always show all sub category regardless of the selected category
2. Once selected a category, clear filters is the only method user has to remove category filter

Fix

1. When selected a category, the selected category will be used to filter sub-category directly related to it.
2. Added an “All category” option as the default selection for category selector
