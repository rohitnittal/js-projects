const apiUrl = 'https://api.example.com/south-india-places';
const placesList = document.getElementById('places-list');

fetch(apiUrl)
	.then(response => response.json())
	.then(data => {
		const places = data.slice(0, 5); // Get first 5 places
		places.forEach(place => {
			const placeHTML = `
				<h2>${place.name}</h2>
				<p>${place.description}</p>
				<img src="${place.image}" alt="${place.name}">
			`;
			placesList.innerHTML += placeHTML;
		});
	})
	.catch(error => console.error('Error:', error));

API Response (JSON):

[
	{
		"name": "Mysore Palace",
		"description": "A historical palace in Mysore, Karnataka",
		"image": "https://example.com/mysore-palace.jpg"
	},
	{
		"name": "Tirupati Temple",
		"description": "A famous temple in Tirupati, Andhra Pradesh",
		"image": "https://example.com/tirupati-temple.jpg"
	},
	{
		"name": "Kochi Beach",
		"description": "A scenic beach in Kochi, Kerala",
		"image": "https://example.com/kochi-beach.jpg"
	},
	{
		"name": "Hogenakkal Falls",
		"description": "A waterfall in Hogenakkal, Tamil Nadu",
		"image": "https://example.com/hogenakkal-falls.jpg"
	},
	{
		"name": "Golkonda Fort",
		"description": "A historical fort in Hyderabad, Telangana",
		"image": "https://example.com/golkonda-fort.jpg"
	}
]
