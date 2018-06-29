---
title: 'Создать новость'
pageconfig:
    parent: /news
    include_username: true
    overwrite_mode: false
pagefrontmatter:
    template: item
    title: 'My new Blog post'
    hero_classes: 'text-light title-h1h2 overlay-dark-gradient hero-large parallax'
    blog_url: /news
    show_sidebar: true
    show_breadcrumbs: true
    show_pagination: true
    taxonomy:
        category:
            - news
        tag:
            - guest
form:
    name: addpage.blogpost
    fields:
        -
            name: title
            label: false
            placeholder: 'Введите заголовок сообщения'
            type: text
            validate:
                required: true
        -
            name: content
            label: false
            type: textarea
            size: long
            classes: editor
        -
            name: images
            label: false
            type: file
            multiple: false
            accept:
                - image/jpeg
            destination: '@self'
            random_name: true
        -
            name: honeypot
            type: honeypot
    buttons:
        -
            type: reset
            value: Очистить
        -
            type: submit
            value: Опубликовать
    process:
        -
            addpage: null
        -
            redirect: /news
---

