---
layout: page
title: Contact us
permalink: /contactus/
order: 50
blocks_before:
  - layout: "block_image_banner"
    image: /assets/images/banner/banner-contactus.jpg
  - layout: "block_text_fluid"
    title: About Standard Hub
    paragraph: The Standard Hubs Work Program (WP) employs a lightweight, working group-focused process where members can create a new work item in less than a week. Working Groups (WGs) define their own process, tools, partnerships and cadence.
  - layout: "block_contactus_mascot"
    form_input:
      - label: "Name"
        type: "text"
      - label: "Surname"
        type: "text"
      - label: "Phone"
        type: "text"
      - label: "Function"
        type: "text"
      - label: "Company"
        type: "text"
      - label: "Your message"
        type: "textarea"
      - label: "How do you hear about us ..."
        type: "select"
        option:
          - key: "ex 1"
            value: "1"
          - key: "ex 2"
            value: "2"
      - label: "Subscriber to our mailing list"
        type: "checkbox"
    button_label: "Submit form"   
---