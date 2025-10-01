---
date: "2025-09-04"
draft: true
omit_header_text: true
title: "Moving beyond folders: Managing document metadata in SharePoint"
featured_image: ""
tags:
  - SharePoint
  - Microsoft
---

I have recently completed some work for a local charity supporting their rollout of SharePoint to replace an old file share. This work reminded me how confusing SharePoint can be for new users, especially when it comes to using it to replace a traditional file server. Out of the box, SharePoint has some fantastic benefits over a file share, such as automatic file versioning, soft deletion support with the multi-stage recycle bin and the ability to easily access and share documents without needed a VPN. But if you just continue to use SharePoint in the same way you did with a file share you are missing out on loads of additional capability.

In this short series of articles I am going to outline three ways you can improve your use of SharePoint to level up document management within your intranet or team site. I am going to start with making use of metadata and leveraging this to create tailored views to help users find the relevant information quickly. In part 2 we will discuss how search-ability and consistency can be improved with the addition of Site Columns and Content Types. Then finally part 3 will introduce Document Sets to keep related documents together and enable them to share metadata. By the end of this series you will be able to design a scalable and searchable document management strategy making the best use of SharePoint features and you'll be able to make all these changes without your SharePoint admin being involved.

So let's kick-off with document library metadata, what is it and why might you want to use it?

## What is metadata?

While it is perfectly acceptable to use a SharePoint Document Library just like a shared folder, all document libraries have the ability to associate additional information with the documents. This is sometimes really useful, because that information is tracked with the document it can remove the need to keep track of it elsewhere. For example, let's say you are storing project documents in a library, you may want to keep track of the project that the document relates to. You may also want to track the name of the client, who the project manager is, what phase the project is in, and what type of document it is. This is all possible using SharePoint metadata within a Document Library. This is what that might look like.

![Project documents in SharePoint](/images/project-documents.png)

---

- What is metadata?
- How do you create it?
- What can you do with it?
  - Filters
  - Views
  - Search
- Challenges with metadata when used across multiple sites or libraries -> fixed in part2
