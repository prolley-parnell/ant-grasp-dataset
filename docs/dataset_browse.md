---
layout: page
title: Browse
sidebar_link: true
sidebar_sort_order: 3
---
{% include datatables.html %}

{% assign mydata=site.data.experiment_database_04-02-25 %}

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