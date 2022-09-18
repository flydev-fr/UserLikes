# UserLikes
Likes system ProcessWire module connected to users.


## Usage example:

```php
<?php namespace ProcessWire;

// get module instance
$likesmod = $modules->get('UserLikes');
// render a 'like' button
$content = $likesmod->render();
// get total likes of the page
$total_likes = $likesmod->getTotal($page->id);
$content .= "Number of likes for this page: " . $total_likes;
// most liked page
$limit = 1;
$mostliked = $likesmod->getMostLikedPage($limit);
if ($total_likes) {
  $content .= "<br />Most liked page: " . $pages->get($mostliked[0]['pageId'])->title . "(" . $mostliked[0]['pageId'] . ") " . " (number of likes: ". $mostliked[0]['likesCount'] . ")";
}
else {
  $content .= "<br />User has not liked this page.";
}
echo $content;
```
