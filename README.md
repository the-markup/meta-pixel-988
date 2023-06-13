# Data for “Suicide Hotlines Promise Anonymity. Dozens of Their Websites Send Sensitive Data to Facebook”

This contains the data for our story "[Suicide Hotlines Promise Anonymity. Dozens of Their Websites Send Sensitive Data to Facebook](https://themarkup.org/pixel-hunt/2023/06/13/suicide-hotlines-promise-anonymity-dozens-of-their-websites-send-sensitive-data-to-facebook)".

Dozens of sites tied to the national crisis hotline transmitted information on visitors through the Meta Pixel.

# Methodology

The Markup tested [hundreds of local crisis center websites](https://988lifeline.org/our-crisis-centers/?_ga=2.88829854.444352967.1678896797-735859738.1677766702) under the umbrella of the national 988 Suicide and Crisis Lifeline. Calls to the national 988 line are routed to these centers based on the area code of the caller. The organizations often also operate their own crisis lines and provide other social services to their communities.

We ran an automated [Blacklight](https://themarkup.org/blacklight) scan on 186 of these sites. You can read more about how Blacklight conducts its scans [here](https://themarkup.org/blacklight/2020/09/22/how-we-built-a-real-time-privacy-inspector).

The results showed that of these sites, 33 employed the Meta tracking pixel.

We then manually inspected the network traffic while visiting these sites. We looked for any network calls to Facebook servers for the following events:

- A **page view** event when the page initially loaded, sending the name of the page, the URL, and a user ID.
- A **button click** event when a user clicked on a button to dial a phone number for help, sending the button text.
- A **form submit** event when a user filled out a contact form, and any form data that is sent.

When we found evidence of any of these taking place, we documented it with a screenshot showing the network activity in the browser’s Developer Tools’ Network activity panel showing the call, and the information sent. We also included a HAR file for the testing session for each site.

In the repository there is a folder for each organization’s website that we tested. Inside the folder are screenshots of relevant data being sent to Facebook via the Meta tracking pixel and [HAR files](https://en.wikipedia.org/wiki/HAR_(file_format)) saved during the process of documenting the data collection.


Questions? Write to us: [keegan@themarkup.org](mailto:keegan@themarkup.org) 





## Data Dictionary: meta-pixel-988-tests.csv
<table border="0" class="dataframe">
  <thead>
    <tr style="text-align: left;">
      <th>Column</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
     <tr>
      <td><strong>organization</strong></td>
      <td>Organization name</td>
    </tr>
     <tr>
      <td><strong>domain</strong></td>
      <td>Organization website</td>
    </tr>
 <tr>
      <td><strong>based_in</strong></td>
      <td>Organization location</td>
    </tr>
     <tr>
      <td><strong>pixel_homepage_fires</strong></td>
      <td>Page view event sent to Facebook</td>
    </tr>
    <tr>
      <td><strong>pixel_phone_click_fires</strong></td>
      <td>Phone number button click event sent to Facebook</td>
    </tr>
    <tr>
      <td><strong>pixel_form_fires</strong></td>
      <td>Contact form data sent to Facebook</td>
    </tr>
  </tbody>
</table>


# Data

**[meta-pixel-988-tests.csv](https://github.com/the-markup/meta-pixel-988/blob/main/meta-pixel-988-tests.csv)**
*2.9 KB. 33 rows. First row is the header.*
