# LaTeX Template for Papers at DHBW CAS

## Features

- Pre-configured to comply with the design guidelines for academic papers in the Wirtschaftsinformatik course of study at DHBW CAS.
- GitHub Template Repository to easily jumpstart a new document.
- GitHub Actions Workflow to build the document and attach the PDF as a realease to the repository when new tags are pushed.

  **Example**:

  ```bash
  # do some changes...
  git commit          # commit your changes
  git tag 1.0         # set a tag
  git push            # push your changes
  git push origin 1.0 # push the tag
  ```
  
  When the tag is pushed a new workflow is triggered that will build the document and create a new release with the PDF as an attached asset using the tag that you have set.
- The LaTeX package [`minted`](https://ctan.org/pkg/minted) for beautifully colored code listings.

  - `python` and the package `Pygments` are required.
  - The PDF needs to be build with the `--shell-escape` flag.
  
  Check the package documentation for further details.
