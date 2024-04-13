# Cool React Hook Form

This fork of [react-hook-form](https://github.com/react-hook-form/react-hook-form) introduces a specific enhancement for handling form inputs: whenever an input field is an empty string, it automatically transforms this value to undefined. This can be particularly useful for simplifying integrations with backend systems that distinguish between empty strings and undefined values, or when applying validations that treat these differently.

### Features

- Automatic Transformation: Automatically convert empty string inputs to undefined, simplifying certain validation and state management scenarios.
- Seamless Integration: Designed to be a drop-in replacement with minimal changes needed for existing React Hook Form implementations.

### Install

    npm install cool-react-hook-form

### Quickstart

```jsx
import { useForm } from 'react-hook-form';

function App() {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } = useForm();

  return (
    <form onSubmit={handleSubmit((data) => console.log(data))}>
      <input {...register('firstName')} />
      <input {...register('lastName', { required: true })} />
      {errors.lastName && <p>Last name is required.</p>}
      <input {...register('age', { pattern: /\d+/ })} />
      {errors.age && <p>Please enter number for age.</p>}
      <input type="submit" />
    </form>
  );
}
```

### Acknowledgments

- Thanks to the original authors and contributors of React Hook Form for providing a solid foundation for this fork.
