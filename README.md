# Willow's group website

The website uses [al-folio](https://alshedivat.github.io/al-folio/). For their original instructions, see [ORIG_README](ORIG_README.md). Here, we maintain a list of (non-obvious) instructions for how to keep the website up to date.

## Instructions for adding / changing contents

To add and change contents, fork the repo, clone it, make changes locally, push, and then do a pull request from your fork to this repository. Always make the pull request to master. Once pull request is merged and the master is updated, the page is automatically rebuilt and deployed (usually takes a few minutes).

### Local installation (optional)

If you want to test changes locally, you can follow [these](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) instructions for installation.

### Adding current team members

- Add your profile picture to [assets/img/team/](assets/img/team/).
- Add entry in [_data/team.yml](_data/team.yml). It doesn't matter where, all members will be sorted by category.
- Specify the name of your profile pic (without path), your position, and the type: "faculty", "postdoc/engineer", "student", "visitor" and "staff".

### Adding former members

To add a former member, remove the profile from [_data/team.yml](_data/team.yml) and add it (in short form, as the other examples there) to [_includes/former_members.liquid](_includes/former_members.liquid) or [_includes/former_visitors.liquid](_includes/former_visitors.liquid), depending on the type.

### Adding seminars

Add entry in [_data/seminars.yml](_data/seminars.yml), following the example there.

You can specify "date," "recording," "slides," "academic_institution," "company," "abstract," and "bio."
