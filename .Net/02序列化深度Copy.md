```C#
public static string Serializable(object target){
    using(MemoryStream stream = new MemoryStream()){
        new BinaryFormatter().Serialize(stream, target);

        return Convert.ToBase64String(stream.ToArray());
    }
}

public static T Desializable<T>(string target){
    byte[] targetArray = Convert.FormBase64String(target);

    using(MemoryStream stream = new MemoryStream(targetArray)){
        return (T)(new BinaryFormatter().Deserialize(stream));
    }
}

public static T DeepClone<T>(T t){
    return Derializable<T>(Serializable(t));
}