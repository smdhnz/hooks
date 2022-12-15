# useZodForm

```ts
import { useForm, FieldValues } from "react-hook-form";
import { zodResolver } from "@hookform/resolvers/zod";
import { AnyZodObject } from "zod";

function useZodForm<T extends FieldValues>(schema: AnyZodObject) {
  return useForm<T>({
    resolver: zodResolver(schema),
  });
}
```
