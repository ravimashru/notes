# Import JSON files

Add the following to the `tsconfig.json` file:

```json
{
	"compilerOptions": {
		"resolveJsonModule": true,
		"esModuleInterop": true
	}
}
```



Then import like this:

```typescript
import ongoingCourses from './data/ongoing.json';
```

