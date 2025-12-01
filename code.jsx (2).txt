import React, { useState } from "react";
import { BrowserRouter as Router, Routes, Route, Link, useParams } from "react-router-dom";

// Home Component
const Home = () => (
  <div style={{ padding: "20px" }}>
    <h1
      style={{
        fontWeight: "bold",
        background: "linear-gradient(to right, blue, purple, orange)",
        WebkitBackgroundClip: "text",
        WebkitTextFillColor: "transparent",
      }}
    >
      Welcome to <span style={{ color: "orange" }}>SWE Institute</span>
    </h1>
    <p>Empowering students with quality education and comprehensive learning resources</p>

    <section style={{ marginTop: "30px" }}>
      <h2>
        <span role="img" aria-label="book">
          📚
        </span>{" "}
        Famous Books & Study Materials
      </h2>

      <div
        style={{
          border: "1px solid #eee",
          padding: "15px",
          borderRadius: "8px",
          maxWidth: "400px",
          marginTop: "10px",
        }}
      >
        <div
          style={{
            width: "40px",
            height: "5px",
            background: "linear-gradient(to right, blue, purple)",
            borderRadius: "3px",
            marginBottom: "8px",
          }}
        />
        <h3>NCERT Mathematics</h3>
        <p>Comprehensive guide for board exam preparation</p>
        <span
          style={{
            backgroundColor: "#f9f1c3",
            padding: "3px 7px",
            borderRadius: "5px",
            fontWeight: "600",
          }}
        >
          Mathematics
        </span>
      </div>
    </section>
  </div>
);

// Class Page Component (for normal classes)
const ClassPage = ({ className }) => {
  const [searchTerm, setSearchTerm] = useState("");

  // Static recent chapters example
  const recentChapters = [
    "Chapter 1: Introduction",
    "Chapter 2: Advanced Concepts",
    "Chapter 3: Practice Problems",
    "Chapter 4: Important Theorems",
  ];

  const filteredChapters = recentChapters.filter((chapter) =>
    chapter.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div style={{ padding: "20px" }}>
      <h2>{className} Class</h2>
      <input
        type="search"
        placeholder="Search chapters..."
        value={searchTerm}
        onChange={(e) => setSearchTerm(e.target.value)}
        style={{
          width: "100%",
          padding: "10px",
          borderRadius: "5px",
          border: "1px solid #ccc",
          marginBottom: "15px",
        }}
      />
      <div>
        <h3>Recent Chapters</h3>
        <ul>
          {filteredChapters.length > 0
            ? filteredChapters.map((chapter, index) => <li key={index}>{chapter}</li>)
            : <li>No chapters found.</li>}
        </ul>
      </div>
    </div>
  );
};

// FAQ Component
const FAQ = () => (
  <div style={{ padding: "20px", maxWidth: "700px" }}>
    <h2>Frequently Asked Questions (FAQ)</h2>
    <p>Here you can provide answers to common questions about SWE Institute.</p>
    <ul>
      <li><strong>Q:</strong> What courses do you offer?<br/><strong>A:</strong> We offer classes from 8th to 12th, JEE, IIT, and NEET preparation.</li>
      <li><strong>Q:</strong> How can I enroll?<br/><strong>A:</strong> Please contact us through the Contact page for enrollment details.</li>
      <li><strong>Q:</strong> Are there online classes?<br/><strong>A:</strong> Yes, we provide online sessions for all classes.</li>
    </ul>
  </div>
);

// About Me Component
const AboutMe = () => (
  <div style={{ padding: "20px", maxWidth: "700px" }}>
    <h2>About Me - Sahil Swe</h2>
    <img
      src="https://via.placeholder.com/150" // Replace with actual photo URL if available
      alt="Sahil Swe"
      style={{ borderRadius: "8px", marginBottom: "15px" }}
    />
    <p><a href="https://via.placeholder.com/150" target="_blank" rel="noopener noreferrer">View full size</a></p>

    <section>
      <h3>Contact me</h3>
      <p><strong>Email:</strong> sahilswe@example.com</p>
      <p>
        <strong>My web page:</strong>{" "}
        <a href="https://sahilswe1.blogspot.com" target="_blank" rel="noopener noreferrer">
          Sahilswe1
        </a>
      </p>
      <p>On Blogger since: May 2020</p>
      <p>Profile views: 226</p>
      <p><a href="#report">Report abuse</a></p>
    </section>

    <section>
      <h3>My blogs</h3>
      <ul>
        <li>SWE INSTITUTE</li>
        <li>Sahil Swe</li>
      </ul>
    </section>

    <section>
      <h3>About me</h3>
      <table style={{ borderCollapse: "collapse", width: "100%" }}>
        <tbody>
          <tr>
            <td><strong>Gender</strong></td><td>Male</td>
          </tr>
          <tr>
            <td><strong>Industry</strong></td><td>Education</td>
          </tr>
          <tr>
            <td><strong>Occupation</strong></td><td>Mentor</td>
          </tr>
          <tr>
            <td><strong>Location</strong></td><td>Srinagar, Jammu and Kashmir, India</td>
          </tr>
          <tr>
            <td><strong>Links</strong></td><td>Wishlist</td>
          </tr>
        </tbody>
      </table>
      <p><strong>Introduction:</strong> I am a dynamic research student, dedicated to mentoring numerous students for competitive exams. My achievements include qualifying in various prestigious exams such as IIT-JAM, CUET, NTSE, EF-SET, and SAT, alongside holding degrees in Physics, Nuclear Engineering, Psychology, and Spectroscopy. With training from esteemed institutions like ISRO and UNICEF, I have also amassed over 150 certifications from top universities like Yale, Stanford, and Microsoft. Beyond my academic and technical prowess, I excel in AI and digital marketing, proficient in AI skills, Python, R, and more. Moreover, I bring a wealth of experience in leadership, communication, problem-solving, and project management, contributing to my well-rounded and accomplished professional profile.</p>
    </section>

    <section>
      <h3>Interests</h3>
      <ul>
        <li>Academic Pursuits: Passionate about studying and continuous learning in diverse fields.</li>
        <li>Writing Skills: Proficient in writing, including academic papers, creative content, and professional documents.</li>
        <li>Research: Experienced in conducting research and exploring new ideas and concepts.</li>
        <li>Sports Enthusiast: Enjoy playing and following cricket and football, showcasing teamwork and sportsmanship.</li>
        <li><strong>Indoor Games:</strong> Skilled in various indoor games, demonstrating strategic thinking and adaptability.</li>
        <li>Outdoor Activities: Enthusiastic about outdoor activities like fishing, reflecting a balanced lifestyle and appreciation for nature.</li>
      </ul>
    </section>

    <section>
      <h3>Favourite Films</h3>
      <p>Hollywood, Web-series, Nickelodeon etc. Beyond my academic and professional endeavors, I have a keen interest in exploring various genres of films and web series. I particularly enjoy sci-fi, technology-themed, romantic, drama, streamline consciousness, and horror mystery genres, finding inspiration and entertainment in their storytelling and themes.</p>
    </section>

    <section>
      <h3>Favourite Music</h3>
      <p>Recitations of Holy Hymnody. My favorite music genres include classical, jazz, electronic, pop, rock, world music, and more. Exploring these diverse styles not only enriches my leisure time but also inspires creativity and perspective in my work.</p>
    </section>

    <section>
      <h3>Favourite Books</h3>
      <p>Islamic and Science, Mythology, Holy Scriptures, Ancient treatise</p>
      <ol>
        <li>"A Brief History of Time" & The Theory of Everything by Stephen Hawking</li>
        <li>"The Origin of Species" by Charles Darwin</li>
        <li>"The Double Helix" by James D. Watson</li>
        <li>"The Structure of Scientific Revolutions" by Thomas S. Kuhn</li>
        <li>"The Selfish Gene" by Richard Dawkins</li>
      </ol>
      <ol start="6">
        <li>"Thinking, Fast and Slow" by Daniel Kahneman</li>
        <li>"Man's Search for Meaning" by Viktor E. Frankl</li>
        <li>"The Power of Habit" by Charles Duhigg</li>
        <li>"Influence: The Psychology of Persuasion" by Robert B. Cialdini</li>
        <li>"Quiet: The Power of Introverts in a World That Can't Stop Talking" by Susan Cain</li>
      </ol>
      <ol start="11">
        <li>"Meditations" by Marcus Aurelius</li>
        <li>"Thus Spoke Zarathustra" by Friedrich Nietzsche</li>
        <li>"The Republic" by Plato</li>
        <li>"Critique of Pure Reason" by Immanuel Kant</li>
        <li>"Zen and the Art of Motorcycle Maintenance" by Robert M. Pirsig</li>
      </ol>
      <h4>5 Best Selling Books:</h4>
      <ol>
        <li>"To Kill a Mockingbird" by Harper Lee</li>
        <li>"The Catcher in the Rye" by J.D. Salinger</li>
        <li>"Harry Potter and the Sorcerer's Stone" by J.K. Rowling</li>
        <li>"The Da Vinci Code" by Dan Brown</li>
        <li>"The Alchemist" by Paulo Coelho</li>
      </ol>
    </section>
  </div>
);

// Contact Component
const Contact = () => (
  <div style={{ padding: "20px", maxWidth: "600px" }}>
    <h2>Contact Us</h2>
    <p>You can reach us through the following means:</p>
    <ul>
      <li><strong>Email:</strong> contact@sweinstitute.com</li>
      <li><strong>Phone:</strong> +91 12345 67890</li>
      <li><strong>Address:</strong> SWE Institute, Srinagar, Jammu and Kashmir, India</li>
    </ul>
    <form style={{ marginTop: "20px" }}>
      <label>
        Name:<br />
        <input type="text" name="name" style={{ width: "100%", padding: "8px", marginBottom: "10px" }} />
      </label>
      <label>
        Email:<br />
        <input type="email" name="email" style={{ width: "100%", padding: "8px", marginBottom: "10px" }} />
      </label>
      <label>
        Message:<br />
        <textarea name="message" rows="5" style={{ width: "100%", padding: "8px", marginBottom: "10px" }} />
      </label>
      <button type="submit" style={{ padding: "10px 15px", backgroundColor: "blue", color: "white", border: "none", borderRadius: "4px" }}>Send</button>
    </form>
  </div>
);

// Notes Landing Page: search + class list (8th to 12th)
const Notes = () => {
  const [searchTerm, setSearchTerm] = useState("");
  const classes = ["8th", "9th", "10th", "11th", "12th"];

  // static notes list example for search generic on notes landing page
  const allNotes = [
    "8th: Introduction to Algebra",
    "9th: Geometry Basics",
    "10th: Physics Fundamentals",
    "11th: Organic Chemistry",
    "12th: Calculus Overview",
  ];
  const filteredNotes = allNotes.filter((note) => note.toLowerCase().includes(searchTerm.toLowerCase()));

  return (
    <div style={{ padding: "20px" }}>
      <h2>Notes</h2>
      <input
        type="search"
        placeholder="Search notes..."
        value={searchTerm}
        onChange={(e) => setSearchTerm(e.target.value)}
        style={{
          width: "100%",
          padding: "10px",
          borderRadius: "5px",
          border: "1px solid #ccc",
          marginBottom: "15px",
        }}
      />
      <div style={{ marginBottom: "20px" }}>
        <h3>Classes</h3>
        <ul style={{ listStyle: "none", paddingLeft: 0, display: "flex", gap: "15px" }}>
          {classes.map((cls) => (
            <li key={cls}>
              <Link to={`/notes/${cls}`} style={{ textDecoration: "none", color: "blue" }}>
                {cls.toUpperCase()}
              </Link>
            </li>
          ))}
        </ul>
      </div>

      <div>
        <h3>Search Results</h3>
        {filteredNotes.length > 0 ? (
          <ul>
            {filteredNotes.map((note, idx) => (
              <li key={idx}>{note}</li>
            ))}
          </ul>
        ) : (
          <p>No notes found.</p>
        )}
      </div>
    </div>
  );
};

// Notes Class Page (8th-12th): search bar + full chapter list
const NotesClassPage = () => {
  const { classId } = useParams();
  const className = classId.toUpperCase();

  const [searchTerm, setSearchTerm] = useState("");

  // Sample data of chapters for each class (customize as needed)
  const chaptersData = {
    "8TH": [
      "Introduction to Algebra",
      "Polynomials",
      "Linear Equations",
      "Geometry Basics",
      "Data Handling",
    ],
    "9TH": [
      "Number Systems",
      "Polynomials",
      "Coordinate Geometry",
      "Lines and Angles",
      "Quadrilaterals",
    ],
    "10TH": [
      "Real Numbers",
      "Triangles",
      "Circles",
      "Algebraic Expressions",
      "Surface Areas and Volumes",
    ],
    "11TH": [
      "Sets",
      "Relations & Functions",
      "Limits & Derivatives",
      "Statics",
      "Thermodynamics",
    ],
    "12TH": [
      "Matrices & Determinants",
      "Integrals",
      "Vectors",
      "Electromagnetism",
      "Probability",
    ],
  };

  const chapters = chaptersData[className] || [];

  // filter by search term
  const filteredChapters = chapters.filter((ch) => ch.toLowerCase().includes(searchTerm.toLowerCase()));

  return (
    <div style={{ padding: "20px" }}>
      <h2>Notes for {className} Class</h2>
      <input
        type="search"
        placeholder="Search chapters..."
        value={searchTerm}
        onChange={(e) => setSearchTerm(e.target.value)}
        style={{
          width: "100%",
          padding: "10px",
          borderRadius: "5px",
          border: "1px solid #ccc",
          marginBottom: "15px",
        }}
      />
      <div>
        <h3>All Chapters</h3>
        {filteredChapters.length > 0 ? (
          <ul>
            {filteredChapters.map((chapter, idx) => (
              <li key={idx}>{chapter}</li>
            ))}
          </ul>
        ) : (
          <p>No chapters found.</p>
        )}
      </div>
    </div>
  );
};

// Main App component
const App = () => {
  const classes = ["8th", "9th", "10th", "11th", "12th", "jee", "iit", "neet"];
  const [settingsOpen, setSettingsOpen] = useState(false);

  const toggleSettings = () => setSettingsOpen((prev) => !prev);

  return (
    <Router>
      <header
        style={{
          display: "flex",
          justifyContent: "space-between",
          alignItems: "center",
          padding: "10px 20px",
          borderBottom: "1px solid #ddd",
          position: "relative",
          flexWrap: "wrap",
        }}
      >
        <div>
          <Link
            to="/"
            style={{ textDecoration: "none", fontWeight: "bold", fontSize: "24px", color: "#666" }}
          >
            <span style={{ color: "blue" }}>SWE</span> <span style={{ color: "purple" }}>Institute</span>
          </Link>
        </div>

        <nav style={{ marginTop: "10px" }}>
          <ul
            style={{
              listStyleType: "none",
              margin: 0,
              padding: 0,
              display: "flex",
              flexWrap: "wrap",
              gap: "15px",
              alignItems: "center",
            }}
          >
            {classes.map((cls) => (
              <li key={cls}>
                <Link to={`/${cls}`} style={{ textDecoration: "none", color: "black" }}>
                  {cls.toUpperCase()}
                </Link>
              </li>
            ))}
            <li>
              <Link to="/notes" style={{ textDecoration: "none", color: "black", fontWeight: "bold" }}>
                Notes
              </Link>
            </li>
          </ul>
        </nav>

        {/* Settings Icon */}
        <div style={{ position: "relative", cursor: "pointer", marginTop: "10px" }}>
          <span
            role="img"
            aria-label="settings"
            onClick={toggleSettings}
            style={{ fontSize: "24px", userSelect: "none" }}
            title="Settings"
          >
            ⚙️
          </span>

          {settingsOpen && (
            <ul
              style={{
                position: "absolute",
                top: "30px",
                right: 0,
                backgroundColor: "white",
                border: "1px solid #ccc",
                borderRadius: "5px",
                listStyle: "none",
                padding: "10px 15px",
                boxShadow: "0 2px 5px rgba(0,0,0,0.15)",
                zIndex: 1000,
                minWidth: "150px",
              }}
            >
              <li style={{ margin: "8px 0" }}>
                <Link
                  to="/faq"
                  onClick={() => setSettingsOpen(false)}
                  style={{ textDecoration: "none", color: "#333" }}
                >
                  FAQ
                </Link>
              </li>
              <li style={{ margin: "8px 0" }}>
                <Link
                  to="/about"
                  onClick={() => setSettingsOpen(false)}
                  style={{ textDecoration: "none", color: "#333" }}
                >
                  About Me
                </Link>
              </li>
              <li style={{ margin: "8px 0" }}>
                <Link
                  to="/contact"
                  onClick={() => setSettingsOpen(false)}
                  style={{ textDecoration: "none", color: "#333" }}
                >
                  Contact
                </Link>
              </li>
              <li style={{ margin: "8px 0" }}>
                <Link
                  to="/notes"
                  onClick={() => setSettingsOpen(false)}
                  style={{ textDecoration: "none", color: "#333" }}
                >
                  Notes
                </Link>
              </li>
            </ul>
          )}
        </div>
      </header>

      <main>
        <Routes>
          <Route path="/" element={<Home />} />
          {classes.map((cls) => (
            <Route key={cls} path={`/${cls}`} element={<ClassPage className={cls.toUpperCase()} />} />
          ))}

          {/* Settings pages */}
          <Route path="/faq" element={<FAQ />} />
          <Route path="/about" element={<AboutMe />} />
          <Route path="/contact" element={<Contact />} />

          {/* Notes pages */}
          <Route path="/notes" element={<Notes />} />
          <Route path="/notes/:classId" element={<NotesClassPage />} />
        </Routes>
      </main>
    </Router>
  );
};

export default App;
