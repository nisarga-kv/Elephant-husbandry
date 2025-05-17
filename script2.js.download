const centerData = {
    "Assam": ["Kaziranga Center", "Manas Center"],
    "Meghalaya": ["Shillong Center"],
    "Arunachal Pradesh": ["Itanagar Center", "Pasighat Center"]
  };
  
  const elephantData = {
    "Kaziranga Center": [
      {
        name: "Rani", age: 32, weight: 2500, health: "Good",
        stress: "Low", nutrition: "Balanced", training: "Advanced",
        image: "ele1.jpg"
      },
      {
        name: "Gaja", age: 40, weight: 2700, health: "Excellent",
        stress: "Medium", nutrition: "Rich", training: "Basic",
        image: "ele2.jpg"
      }
    ],
    "Manas Center": [
      {
        name: "Lakshmi", age: 29, weight: 2450, health: "Fair",
        stress: "High", nutrition: "Moderate", training: "Intermediate",
        image: "ele3.jpg"
      }
    ],
    "Shillong Center": [
      {
        name: "Bahadur", age: 35, weight: 2600, health: "Good",
        stress: "Low", nutrition: "Balanced", training: "Advanced",
        image: "ele4.jpg"
      }
    ],
    "Itanagar Center": [
      {
        name: "Moti", age: 30, weight: 2550, health: "Excellent",
        stress: "Low", nutrition: "High", training: "Advanced",
        image: "ele5.jpg"
      }
    ],
    "Pasighat Center": [
      {
        name: "Chintu", age: 28, weight: 2400, health: "Good",
        stress: "Medium", nutrition: "Moderate", training: "Intermediate",
        image: "ele6.jpg"
      }
    ]
  };
  
  function populateCenters() {
    const location = document.getElementById("location").value;
    const centerSelect = document.getElementById("center");
    centerSelect.innerHTML = "";
    if (location && centerData[location]) {
      centerData[location].forEach(center => {
        const option = document.createElement("option");
        option.value = center;
        option.textContent = center;
        centerSelect.appendChild(option);
      });
    }
  }
  
  function fetchResults() {
    const center = document.getElementById("center").value;
    const loader = document.getElementById("loader");
    const results = document.getElementById("resultsContainer");
    results.innerHTML = "";
    loader.style.display = "block";
  
    setTimeout(() => {
      loader.style.display = "none";
      if (!center || !elephantData[center]) {
        results.innerHTML = "<p>No data found for the selected center.</p>";
        return;
      }
  
      elephantData[center].forEach(elephant => {
        const card = document.createElement("div");
        card.className = "card";
        card.innerHTML = `
          <img src="${elephant.image}" alt="${elephant.name}" />
          <div class="card-content">
            <h3>${elephant.name}</h3>
            <p>Age: ${elephant.age}</p>
            <p>Weight: ${elephant.weight} kg</p>
            <button onclick='viewDetails(${JSON.stringify(elephant)})'>View Profile</button>
          </div>
        `;
        results.appendChild(card);
      });
    }, 1000);
  }
  
  function viewDetails(elephant) {
    const modal = document.getElementById("elephantModal");
    const modalContent = document.getElementById("modalDetails");
    modalContent.innerHTML = `
      <h2>${elephant.name}</h2>
      <img src="${elephant.image}" alt="${elephant.name}" style="width:100%; border-radius: 10px; margin-bottom: 10px;">
      <p><strong>Age:</strong> ${elephant.age}</p>
      <p><strong>Weight:</strong> ${elephant.weight} kg</p>
      <p><strong>Health:</strong> ${elephant.health}</p>
      <p><strong>Stress Status:</strong> ${elephant.stress}</p>
      <p><strong>Nutrition:</strong> ${elephant.nutrition}</p>
      <p><strong>Training:</strong> ${elephant.training}</p>
    `;
    modal.style.display = "block";
  }
  
  function closeModal() {
    document.getElementById("elephantModal").style.display = "none";
  }
  
  function scrollToSection(sectionId) {
    const section = document.getElementById(sectionId);
    if (section) {
      section.scrollIntoView({ behavior: "smooth" });
    }
  }
