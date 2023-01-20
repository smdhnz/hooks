# useZodForm
<details>
  <summary>expand</summary>
  ```ts
  import { zodResolver } from "@hookform/resolvers/zod";
  import { useForm, type UseFormProps } from "react-hook-form";
  import { z } from "zod";

  function useZodForm<TSchema extends z.ZodType>(
    props: Omit<UseFormProps<TSchema["_input"]>, "resolver"> & {
      schema: TSchema;
    }
  ) {
    const form = useForm<TSchema["_input"]>({
      ...props,
      resolver: zodResolver(props.schema, undefined),
    });

    return form;
  }

  export { useZodForm };
  ```
 </details>
