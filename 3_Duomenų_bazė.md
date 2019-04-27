Panaudosime `h2` duomenų bazę.


Aprašome klasę kuri atitiks lentelės kurioje saugosime duomenis schemą:

```
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class ListEntity {
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    private Long id;
    private String key;
    private String value;

    public ListEntity() {
    }

    public ListEntity(String key, String value) {
        this.key = key;
        this.value = value;
    }

    public Long getId() {
        return id;
    }

    public String getKey() {
        return key;
    }

    public void setKey(String key) {
        this.key = key;
    }

    public String getValue() {
        return value;
    }

    public void setValue(String value) {
        this.value = value;
    }
}
```

Aprašome repozitorijos interface (sąsają)
```
import org.springframework.data.jpa.repository.JpaRepository;

public interface ListRepository extends JpaRepository<ListEntity, Long> {

}
```

Norint naudoti repozitoriją iš controller klasės ją reikia įterpti naudojant `dependency injection`. Tam aprašomas laukas ir pridedamas konstruktorius reikalaujantis repozitorijos kaip parametro:
```

    private final ListRepository listRepository;

    @Autowired
    public ListController(ListRepository listRepository) {
        this.listRepository = listRepository;
    }
```

Taip įterpus repozitoriją controllerio metoduose galima naudoti įvairius sugeneruotus metodus, jų sąrašas yra pasiekamas 
`JpaRepository` interface dokumentacijoe.

Svarbiausi:
```
	/**
	 * Saves a given entity. Use the returned instance for further operations as the save operation might have changed the
	 * entity instance completely.
	 *
	 * @param entity must not be {@literal null}.
	 * @return the saved entity will never be {@literal null}.
	 */
	<S extends T> S save(S entity);


    	/**
	 * Retrieves an entity by its id.
	 *
	 * @param id must not be {@literal null}.
	 * @return the entity with the given id or {@literal Optional#empty()} if none found
	 * @throws IllegalArgumentException if {@code id} is {@literal null}.
	 */
	Optional<T> findById(ID id);
```


Užduotis:
Saugoti duomenis į repozitoriją naudojant POST metodą
Patyrinėti anotacijas naudotas ant `ListEntity` klasės
