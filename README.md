# SpringBoot-Jackson

#### Custom Serializer on the Class

<b>

```sql

@Data
@JsonSerialize(using = CustomPayload.CustomPayloadSerializer.class)
public class CustomPayload implements Serializable {
	
	private static final long serialVersionUID = 1L;
	
	private String name;
	private String displayName;
	private String displayValue;
	
	public static class CustomPayloadSerializer extends JsonSerializer<CustomPayload> {

		@Override
		public void serialize(CustomPayload value, JsonGenerator generator, SerializerProvider serializers)
				throws IOException {
			generator.writeStartObject();
			generator.writeStringField("name", value.getName());
			generator.writeStringField(value.getDisplayName(), value.getDisplayValue());
			generator.writeEndObject();
		}
		
	}

}

```

</b>

#### Custom Serializer on the ObjectMapper

#### Custom Serializer with @JsonComponent 
