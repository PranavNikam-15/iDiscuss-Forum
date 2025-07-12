<h2>🧩 Database Schema</h2>

<h3>Users Table</h3>
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Column</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>user_id</td><td>INT (PK)</td><td>Unique user ID</td></tr>
    <tr><td>user_name</td><td>VARCHAR(50)</td><td>User's name</td></tr>
    <tr><td>user_email</td><td>VARCHAR(150)</td><td>Unique email</td></tr>
    <tr><td>user_password</td><td>VARCHAR(255)</td><td>Hashed password</td></tr>
    <tr><td>user_profile</td><td>VARCHAR(255)</td><td>Filename of profile image</td></tr>
    <tr><td>bio</td><td>TEXT</td><td>User bio</td></tr>
    <tr><td>birthdate</td><td>DATE</td><td>Date of birth</td></tr>
    <tr><td>gender</td><td>ENUM</td><td>'Male', 'Female', 'Other'</td></tr>
    <tr><td>organization</td><td>VARCHAR(100)</td><td>College/University/Company</td></tr>
    <tr><td>role</td><td>VARCHAR(50)</td><td>Role (e.g. Student, Dev, etc.)</td></tr>
    <tr><td>alt_email</td><td>VARCHAR(150)</td><td>Alternate email</td></tr>
    <tr><td>mobile</td><td>VARCHAR(15)</td><td>Mobile number</td></tr>
    <tr><td>timestamp</td><td>DATETIME</td><td>Created time</td></tr>
  </tbody>
</table>

<h3>Categories Table</h3>
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Column</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>id</td><td>INT (PK)</td><td>Category ID</td></tr>
    <tr><td>name</td><td>VARCHAR(35)</td><td>Category name</td></tr>
    <tr><td>description</td><td>TEXT</td><td>Category description</td></tr>
    <tr><td>timestamp</td><td>DATETIME</td><td>Created time</td></tr>
  </tbody>
</table>

<h3>Threads Table</h3>
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Column</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>thread_id</td><td>INT (PK)</td><td>Thread ID</td></tr>
    <tr><td>thread_title</td><td>VARCHAR(100)</td><td>Title</td></tr>
    <tr><td>thread_desc</td><td>TEXT</td><td>Thread description</td></tr>
    <tr><td>thread_cat_id</td><td>INT (FK)</td><td>Linked category</td></tr>
    <tr><td>thread_user_id</td><td>INT (FK)</td><td>Author of the thread</td></tr>
    <tr><td>timestamp</td><td>DATETIME</td><td>Time posted</td></tr>
  </tbody>
</table>
<p><strong>🔍 Note:</strong> Fulltext index on <code>thread_title</code> and <code>thread_desc</code> enables search.</p>

<h3>Comments Table</h3>
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Column</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>comment_id</td><td>INT (PK)</td><td>Comment ID</td></tr>
    <tr><td>comment_content</td><td>TEXT</td><td>Comment text</td></tr>
    <tr><td>thread_id</td><td>INT (FK)</td><td>Related thread</td></tr>
    <tr><td>comment_by</td><td>INT (FK)</td><td>Comment author</td></tr>
    <tr><td>comment_time</td><td>DATETIME</td><td>Time of comment</td></tr>
  </tbody>
</table>