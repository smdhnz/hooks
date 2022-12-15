# useZodForm

```ts
// yarn add react-hook-form @hookform/resolvers zod

import { useForm, FieldValues } from "react-hook-form";
import { zodResolver } from "@hookform/resolvers/zod";
import { AnyZodObject } from "zod";

function useZodForm<T extends FieldValues>(schema: AnyZodObject) {
  return useForm<T>({
    resolver: zodResolver(schema),
  });
}

// Usage

import { z } from "zod";

const schema = z.object({
  inputText: z.string().min(1)
})

type Schema = z.infer<typeof schema>

const {
  register,
  handleSubmit,
  formState: { errors },
} = useZodForm<Schema>(schema);
```
