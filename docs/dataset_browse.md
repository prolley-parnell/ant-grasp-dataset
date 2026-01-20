---
layout: page
title: Browse
sidebar_link: true
sidebar_sort_order: 3
---
{% include datatables.html %}

This table shows the full verbal descriptions of the video dataset, as well as the assigned tags.

{% assign mydata=site.data.dataset_description %}

<table>
    <caption>Full table of available experiments</caption>
    <thead>
    {% for column in mydata[0] %}
        <th>{{ column[0] }}</th>
    {% endfor %}
    </thead>
    <tbody>
    {% for row in mydata %}
        <tr>
        {% for cell in row %}
            <td>{{ cell[1] }}</td>
        {% endfor %}
        </tr>
    {% endfor %}
    </tbody>
</table>{: .datatable}