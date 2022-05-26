## CSS prefers-reduced-data security & privacy self-review

[2.1 What information might this feature expose to Web sites or other parties, and for what purposes is that exposure necessary?](https://www.w3.org/TR/security-privacy-questionnaire/#purpose)

The feature exposes whether or not a user is browsing in a data saver mode, this
is so website's can respect the user's preference and ship alternative, lighter
assets.

[2.2 Do features in your specification expose the minimum amount of information necessary to enable their intended uses?](https://www.w3.org/TR/security-privacy-questionnaire/#minimum-data)

Yes. It's only if user's are in a reduced state or not. It's not known if this
setting is turned on via the browser, the operating system, or other method.
It's as ambiguous and it can be while still being useful to developers and
designers.

[2.3 How do the features in your specification deal with personal information, personally-identifiable information (PII), or information derived from them?](https://www.w3.org/TR/security-privacy-questionnaire/#personal-data)

The spec makes the user setting ambiguous, to reduce the surface area of
fingerprinting.

[2.4 How do the features in your specification deal with sensitive information?](https://www.w3.org/TR/security-privacy-questionnaire/#sensitive-data)

Sensitive information is made as vague as possible.

[2.5 Do the features in your specification introduce new state for an origin that persists across browsing sessions?](https://www.w3.org/TR/security-privacy-questionnaire/#persistent-origin-specific-state)

No

[2.6 Do the features in your specification expose information about the underlying platform to origins?](https://www.w3.org/TR/security-privacy-questionnaire/#underlying-platform-data)

No

[2.7 Does this specification allow an origin to send data to the underlying platform?](https://www.w3.org/TR/security-privacy-questionnaire/#send-to-platform)

No

[2.8 Do features in this specification enable access to device sensors?](https://www.w3.org/TR/security-privacy-questionnaire/#sensor-data)

No

[2.9 Do features in this specification enable new script execution/loading mechanisms?](https://www.w3.org/TR/security-privacy-questionnaire/#string-to-script)

No

[2.10 Do features in this specification allow an origin to access other devices?](https://www.w3.org/TR/security-privacy-questionnaire/#remote-device)

No

[2.11 Do features in this specification allow an origin some measure of control over a user agent’s native UI?](https://www.w3.org/TR/security-privacy-questionnaire/#native-ui)

No

[2.12 What temporary identifiers do the features in this specification create or expose to the web?](https://www.w3.org/TR/security-privacy-questionnaire/#temporary-id)

No

[2.13 How does this specification distinguish between behavior in first-party and third-party contexts?](https://www.w3.org/TR/security-privacy-questionnaire/#first-third-party)

This feature does not distinguish.

[2.14 How do the features in this specification work in the context of a browser’s Private Browsing or Incognito mode?](https://www.w3.org/TR/security-privacy-questionnaire/#private-browsing)

The feature behaves the same.

[2.15 Does this specification have both "Security Considerations" and "Privacy Considerations" sections?](https://www.w3.org/TR/security-privacy-questionnaire/#considerations)

No

[2.16 Do features in your specification enable origins to downgrade default security protections?](https://www.w3.org/TR/security-privacy-questionnaire/#relaxed-sop)

No

[2.17 How does your feature handle non-"fully active" documents?](https://www.w3.org/TR/security-privacy-questionnaire/#non-fully-active)

No effect

[2.18 What should this questionnaire have asked?](https://www.w3.org/TR/security-privacy-questionnaire/#missing-questions)

Questions above covered things well.
