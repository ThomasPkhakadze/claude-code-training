# Exercise 5: Debug the Broken Dashboard (Developer Track)

## Objective

A colleague built a social media analytics dashboard for a client, but the client reported several issues. Your job is to find and fix all 6 bugs using Claude Code.

The broken file is `broken_dashboard.html` in this folder. Open it in your browser first to see the problems, then use Claude Code to investigate and fix them.

## What the Client Reported

The client sent these complaints in an email:

1. **"The page layout is completely broken -- everything is stacked wrong."**
   Something is causing the page structure to collapse. Sections that should be side by side or properly contained are overlapping or stacking incorrectly.

2. **"The bar chart shows nothing -- just an empty space where the chart should be."**
   The chart area is visible but the chart itself never renders. There should be a bar chart showing monthly trends.

3. **"One of the stat cards is missing from the grid."**
   The dashboard should have stat cards, but the grid layout looks off -- there's a visible gap where a card should be, or the cards don't fill their row properly.

4. **"The numbers in the table don't add up to the total shown in the stat card."**
   If you manually add up the spend values in the ad table, the sum doesn't match the "Total Spend" number shown in the stat card above.

5. **"The fonts look wrong -- not the professional ones we usually use."**
   The page should use Montserrat (our standard agency font), but everything is rendering in a generic system font instead.

6. **"There's a weird dollar sign showing in the background."**
   Instead of the dark background color, some element has a dollar sign character appearing in the CSS, causing a visual glitch.

## Instructions

1. Open `broken_dashboard.html` in your browser to see the current state
2. Open Claude Code and ask it to read the file and find the bugs
3. Fix each bug one at a time, verifying in the browser after each fix
4. Make sure all 6 issues are resolved

## Success Criteria

- [ ] Page layout is properly structured (no collapsed/overlapping sections)
- [ ] Bar chart renders and shows data
- [ ] Stat cards display correctly in their grid with no awkward gaps
- [ ] Table spend values add up to the total shown in the stat card
- [ ] Montserrat font loads and applies correctly
- [ ] Background color renders properly with no dollar sign artifacts
- [ ] Dashboard looks professional and complete after all fixes

## Tips

- Start by reading the HTML source code carefully -- some bugs are in the HTML structure, some in CSS, some in JavaScript
- The browser's Developer Tools (right-click > Inspect) can help you spot CSS issues and JavaScript errors
- Check the Console tab for JavaScript errors (the chart bug will likely show an error there)
- Compare numbers manually -- add up the table values with a calculator
- Look at the `<head>` section for external resource loading issues

## How This Relates to Real Work

These are all real categories of bugs that show up in production dashboards:
- **Structural HTML errors** (missing tags) break layout in subtle ways
- **ID mismatches** between HTML and JavaScript are extremely common
- **CSS value typos** can be hard to spot in a large stylesheet
- **Data inconsistencies** between summary numbers and detail tables erode client trust
- **External resource loading failures** (fonts, scripts) degrade the user experience

Learning to spot these patterns quickly is a valuable developer skill.
