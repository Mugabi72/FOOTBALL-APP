You’ve done the setup correctly. The page says “GitHub Pages source saved”, and your site is being built from the main branch. Now you wait for GitHub to publish it.

Wait 1 to 2 minutes.
Refresh this page (press F5). A box should appear at the top saying “Your site is live at…” with a Visit site button.
Click Visit site. Your link will look like https://mugabi72.github.io/FOOTBALL-APP/.

If the box hasn’t appeared after a few minutes, click the Actions tab at the top of the repo. You’ll see a build running. A green tick means it’s finished, and a refresh of the Pages settings will then show your link.

You can also open this address directly in a new tab:

https://mugabi72.github.io/FOOTBALL-APP/

If it shows a 404 error, wait another minute or two and try again.

When your site loads, copy that link and send it to whoever needs to see your work. Remember the typo fix from earlier: change “Machester” to “Manchester” in index.html, then run git add ., git commit -m "Fix names" and git push. The live site will update by itself.

it is showing that hw can i make videos and pictures of people playing

Adding a media gallery for people playing to the site.

Your website is live, and the pitch, the ELLY name and the ball all look good. Here’s how to add pictures and videos.

Step 1: Upload your files

In Codespaces, right-click the empty space in the Explorer and choose New Folder. Name it media.
Drag your photos and videos from your computer into that folder. Use short names with no spaces, like goal1.jpg and match1.mp4.
Keep each video under about 25 MB so the site loads fast. GitHub rejects files over 100 MB. For long videos, upload to YouTube and use the embed code in Step 3.

Step 2: Add the style
In index.html, find footer{ inside the <style> section and paste this just above it:

css
.gallery{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px}
.gallery img,.gallery video,.gallery iframe{width:100%;aspect-ratio:4/3;object-fit:cover;border-radius:6px;border:4px solid var(--chalk);background:#000}

Step 3: Add the gallery section
Find <section id="xi"> and paste this just above it:

html
<section id="gallery">
  <h2>On the <em>pitch</em></h2>
  <div class="gallery">
    <img src="media/goal1.jpg" alt="Players in a match">
    <img src="media/team.jpg" alt="Team photo">
    <video src="media/match1.mp4" controls></video>
    <iframe src="https://www.youtube.com/embed/VIDEO_ID" allowfullscreen></iframe>
  </div>
</section>

Change the file names to match yours. Replace VIDEO_ID with the code at the end of your YouTube link, or delete that line if you don’t need it.

Step 4: Add it to the menu
Find the <a href="#xi">My XI</a> line and add this after it:

html
<a href="#gallery">Gallery</a>

Step 5: Publish
Press Ctrl + S, then run these in the terminal:

bash
git add .
git commit -m "Add gallery"
git push

Wait a minute or two, then refresh your live site.

Use your own photos and videos, or ones you have permission to use. I can also make the gallery open each picture in a bigger view when you click it.
