# Rugs

## Architecture proposal (static site + Shopify checkout)

### Goals
- Keep the entire experience simple, fast, and on one page for browsing.
- Allow image/logo upload, size selection, and price preview before checkout.
- Redirect to Shopify only at the moment of purchase to keep checkout seamless.
- Showcase a portfolio of ready-made rugs alongside custom requests.

### Recommended structure

#### 1) Static marketing + catalog site (this repo)
Host on GitHub Pages / Netlify / Vercel. The site contains:
- **Home / Collection**: a full catalog grid of ready-made rugs (already present).
- **Product detail sections**: inline or modal product details for sizing, materials, and lead times.
- **Custom order section**: upload image/logo, pick sizing, and see estimated pricing.
- **Portfolio**: completed work and customer highlights.

#### 2) Custom order intake (form + image upload)
Add a lightweight form handler:
- **Form**: Netlify Forms or Formspree.
- **Upload**: Cloudinary or S3-compatible storage.
- **Processing**: store uploads and send the owner an email + a link to the file.

#### 3) Shopify for checkout only
- Products are mirrored in Shopify (same names/prices).
- The site uses **Buy Buttons** or direct **Shopify product links** for checkout.
- Customer clicks “Buy” on the static site → lands on Shopify product page/checkout.

### Page-level layout suggestion (single-page experience)
1. **Hero**
2. **Featured / Ready-to-Ship Rugs**
3. **Custom Rug Builder (simple)**
   - Upload reference image
   - Select size (preset dropdown)
   - Show estimated price
   - Submit custom request
4. **Portfolio / Past Work**
5. **About / Process**
6. **FAQ**
7. **Contact**

### Data flow (simple & scalable)
1. Customer browses products on the static site.
2. Selecting “Buy Now” redirects to Shopify product link.
3. Custom requests:
   - Image + form submission → stored in Cloudinary/S3.
   - Email sent to owner with details and quote request.

### Cost estimate (yearly rough ranges)
- **Hosting**: $0–$200
- **Domain**: $12–$20
- **Form handling**: $0–$240
- **Image storage**: $0–$120
- **Shopify**: $39/mo (Basic) = $468/year

Estimated total: **$520–$1,000/year** depending on traffic and plan.

### Implementation checklist
- [ ] Add upload + size selector + pricing estimate to the custom order form.
- [ ] Add portfolio section with real project images.
- [ ] Add Shopify Buy Buttons or product links for each rug.
- [ ] Connect form submissions to Netlify Forms/Formspree + Cloudinary/S3.
- [ ] Update copy to explain custom order flow + lead times.
