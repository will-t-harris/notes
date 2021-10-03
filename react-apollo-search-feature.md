```jsx
const SEARCH_CLUBS = gql`
  query searchClubs {
    clubs {
      name
      urlSlug
      category {
        urlSlug
      }
    }
  }
`;

  const [searchResults, setSearchResults] = useState([]);
  const { data, loading, error } = useQuery(SEARCH_CLUBS);

  const handleSearch = (event) => {
    const { value } = event.target;

	// clear results if input is empty
    if (value === "") {
      setSearchResults([]);
      return;
    }

    const matchingClubs = data.clubs.filter(({ name }) =>
      name.toLowerCase().includes(value.toLowerCase())
    );

    setSearchResults(matchingClubs);
  };
```