# Web Fundamentals and UX Design - Unit 1 Notes

## **Introduction to the Internet**
- **Definition**: The largest network in the world, connecting individual networks globally.
  - Moves ideas and information through cyberspace.
  - Applications: Sending emails, uploading/downloading files, web surfing.

### **History of the Internet**
1. **1950s-1960s**: Precursors
   - ARPANET developed by the U.S. Department of Defense's ARPA.
2. **1969**: Birth of ARPANET
   - First operational network connecting four U.S. universities.
   - First message: "LOGIN."
3. **1970s**: TCP/IP and Email
   - Vint Cerf and Bob Kahn develop TCP/IP.
   - Email program created.
4. **1980s**: Expanding the Network
   - Term "Internet" coined.
   - Domain Name System (DNS) introduced.
5. **1990s**: Commercialization and WWW
   - World Wide Web invented by Tim Berners-Lee.
   - Web browsers like Mosaic and Netscape Navigator.
6. **2000s**: Broadband and Social Media
   - Broadband becomes widespread.
   - Social media platforms emerge (e.g., Facebook, YouTube).
7. **2010s**: Mobile Internet and IoT
   - Smartphone proliferation and cloud computing.
   - IoT devices connected to the internet.
8. **2020s**: Ongoing Evolution
   - Internet connectivity reaches remote areas.
   - 5G networks, AI, blockchain, and AR emerge.

---

## **IP Addressing**
- **Definition**: A numerical label assigned to devices using the Internet Protocol.
- **Types**:
  - **IPv4**: 32-bit address, 4 octets (0-255).
  - **IPv6**: 128-bit address, 8 fields (hexadecimal).

### **Uniform Resource Locators (URLs)**
- Four-part structure:
  1. Transfer protocol (e.g., HTTP).
  2. Domain name.
  3. Pathname (folder or directory).
  4. File name.

---

## **Domain Name System (DNS)**
- Resolves human-readable domain names to IP addresses.
- **Parts of a domain name**:
  - **Subdomain**: e.g., `www`.
  - **Second-Level Domain (SLD)**: e.g., `example`.
  - **Top-Level Domain (TLD)**: e.g., `.com`.

---

## **HTTP (Hypertext Transfer Protocol)**
- Governs data transfer between a web client and a web server.
- **Features**:
  - Request-response model.
  - Stateless.
  - Text-based protocol.

### **HTTP Methods**
- **GET**: Retrieve data.
- **POST**: Send data to create or update resources.
- **PUT**: Update resources.
- **DELETE**: Remove resources.
- **HEAD**: Retrieve headers only.

### **HTTP Status Codes**
- **200 OK**: Successful request.
- **404 Not Found**: Resource not found.
- **500 Internal Server Error**: Server encountered an error.

---

## **Web Server and Client**
- **Web Server**:
  - Stores and delivers web pages (e.g., Apache, Nginx).
  - Processes requests and sends responses.
- **Web Client (Browser)**:
  - Sends requests to web servers and renders responses.
  - Examples: Google Chrome, Mozilla Firefox.

---

## **HTML (HyperText Markup Language)**
- **Definition**: Standard markup language for creating web pages.
- **Structure**:
  ```html
  <!DOCTYPE html>
  <html>
    <head>
      <title>Title</title>
    </head>
    <body>
      Content here
    </body>
  </html>
  ```

### **HTML Elements**
- Consist of a start tag, content, and an end tag.
- **Example**:
  ```html
  <h1>My First Heading</h1>
  <p>My first paragraph.</p>
  ```

### **Semantic HTML Elements**
- Clearly define content meaning (e.g., `<article>`, `<section>`).

### **Block-Level vs Inline Elements**
- **Block-Level**: Start on a new line (e.g., `<div>`, `<p>`).
- **Inline**: Remain on the same line (e.g., `<span>`, `<a>`).

---

## **HTML Forms**
- Allow user input, submitted to a server.
- **Form Elements**:
  - `<input>`: Text, password, radio buttons, etc.
  - `<textarea>`: Multi-line text input.
  - `<select>`: Dropdown lists.

### **Form Attributes**
- **method**: `GET` (default) or `POST`.
- **action**: URL to process form data.
- **autocomplete**: `on` or `off`.

---

## **Tables in HTML**
- **Structure**:
  ```html
  <table>
    <tr>
      <th>Header</th>
    </tr>
    <tr>
      <td>Data</td>
    </tr>
  </table>
  ```
- Elements:
  - `<tr>`: Table row.
  - `<td>`: Table data.
  - `<th>`: Table header.

---

## **Advanced HTML Inputs (HTML5)**
- **New Types**:
  - `date`, `time`, `email`, `range`, `color`, etc.
- Browser support may vary.

---

## **Organizations Driving Web Standards**
- **IETF**: Develops internet standards.
- **W3C**: Develops web-related technologies and standards.

---

## **Summary**
This unit covered the fundamentals of the internet, protocols, HTML structure, forms, and standards. With these concepts, you can understand and build basic web applications.

---

## **HTML Example Program**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Web Fundamentals Example</title>
  </head>
  <body>
    <!-- Header -->
    <header>
      <h1>Welcome to Web Fundamentals</h1>
      <nav>
        <a href="#section1">Introduction</a> |
        <a href="#section2">Forms</a> |
        <a href="#section3">Tables</a>
      </nav>
    </header>

    <!-- Main Content -->
    <main>
      <section id="section1">
        <h2>Introduction</h2>
        <p>The internet is a global network connecting millions of devices.</p>
      </section>

      <section id="section2">
        <h2>Forms</h2>
        <form action="/submit" method="POST">
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required><br>

          <label for="email">Email:</label>
          <input type="email" id="email" name="email" required><br>

          <label for="gender">Gender:</label><br>
          <input type="radio" id="male" name="gender" value="male">
          <label for="male">Male</label><br>
          <input type="radio" id="female" name="gender" value="female">
          <label for="female">Female</label><br>

          <label for="hobbies">Hobbies:</label><br>
          <input type="checkbox" id="reading" name="hobbies" value="reading">
          <label for="reading">Reading</label><br>
          <input type="checkbox" id="sports" name="hobbies" value="sports">
          <label for="sports">Sports</label><br>

          <input type="submit" value="Submit">
        </form>
      </section>

      <section id="section3">
        <h2>Tables</h2>
        <table border="1">
          <tr>
            <th>Name</th>
            <th>Age</th>
            <th>Country</th>
          </tr>
          <tr>
            <td>John Doe</td>
            <td>30</td>
            <td>USA</td>
          </tr>
          <tr>
            <td>Jane Smith</td>
            <td>25</td>
            <td>UK</td>
          </tr>
        </table>
      </section>
    </main>

    <!-- Footer -->
    <footer>
      <p>&copy; 2025 Web Fundamentals</p>
    </footer>
  </body>
</html>
```
