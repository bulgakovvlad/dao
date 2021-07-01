---
Описание: >-
  На этой странице показано, как использовать строку запроса для изменения
  цвета и размера значка ISCN.
---

# Значок ISCN

**Вы можете добавить одну из следующих строк запроса после знака "`?`" в базовом URL-адресе ниже. Базовый URL:**   
[`https://static.like.co/badge/iscn/dev/<iscn_hash>.svg?`](https://static.like.co/badge/iscn/dev/<iscn_hash>.svg?)\`\`

Пример: [https://static.like.co/badge/iscn/dev/976F3D3D32F32B2496E5D48273A61080F08F8C3A40F7EFDB878519107787DF12.svg?dark=1&responsive=0&width=82](https://static.like.co/badge/iscn/dev/976F3D3D32F32B2496E5D48273A61080F08F8C3A40F7EFDB878519107787DF12.svg?dark=1&responsive=0&width=82)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Строка запроса</th>
      <th style="text-align:left">Принимаемое значение</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">dark</td>
      <td style="text-align:left">
        <p>boolean - например 0 (светлый) or 1 (темный)</p>
        <p>Если не указано - принимает значение по умолчанию = 0.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">responsive</td>
      <td style="text-align:left">
        <p>boolean - например 0 (размер не адаптивный) or 1 (адаптивный размер)</p>
        <p>Если не указано - принимает значение по умолчанию = 0.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">width</td>
      <td style="text-align:left">
        <p>number - например 164 (164px)</p>
        <p>Если не указано - принимает значение по умолчанию = 164.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">height</td>
      <td style="text-align:left">
        <p>number - например 64 (64px)</p>
        <p>Если не указано - принимает значение по умолчанию = 64.</p>
      </td>
    </tr>
  </tbody>
</table>

**Некоторые ошибки могут возникать при предоставлении нескольких конфликтующих значений строки запроса между размером, шириной и высотой.**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Ситуация с ошибкой</th>
      <th style="text-align:left">Код ошибки &amp; Объяснение</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">responsive=1&amp;width=30</td>
      <td style="text-align:left">400
        <br />Не ясно, хочет ли пользователь фиксированный или адаптивный размер.</td>
    </tr>
    <tr>
      <td style="text-align:left">responsive=1&amp;height=20</td>
      <td style="text-align:left">400
        <br />Не ясно, хочет ли пользователь фиксированный или адаптивный размер.</td>
    </tr>
    <tr>
      <td style="text-align:left">responsive=0&amp;height=sf</td>
      <td style="text-align:left">
        <p>400</p>
        <p>Высота в неправильном формате (NaN).</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">responsive=0&amp;wodth=sf</td>
      <td style="text-align:left">
        <p>400</p>
        <p>Высота в неправильном формате (NaN).</p>
      </td>
    </tr>
  </tbody>
</table>

**Примечание:** 

Если указать как высоту, так и ширину, но соотношение не будет соответствовать 164 \(width\) \* 64 \(height\), размер значка будет определен по значению **width**.  
Например, при указании `width=200&height=400`, размер значка составит: `width=200&height=200*64/164`.



