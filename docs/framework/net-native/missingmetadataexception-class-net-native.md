---
title: MissingMetadataException-Klasse (.NET Native)
ms.date: 03/30/2017
ms.assetid: 408f25c4-6d60-475c-92b1-7b52b777c6db
ms.openlocfilehash: d73d66529bc30358c946eb0a7072f0cb8910b19a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128287"
---
# <a name="missingmetadataexception-class-net-native"></a>MissingMetadataException-Klasse (.NET Native)

**.Net für Windows-Apps für Windows 10, nur .net Native**

Die Ausnahme, die ausgelöst wird, wenn Reflektion verwendet wird, um Metadaten abzurufen, die nicht vorhanden sind.

**Namespace:** System.Reflection

> [!IMPORTANT]
> Die- `MissingMetadataException` Klasse ist ausschließlich für die interne Verwendung durch die .net Native-Toolkette vorgesehen. Sie ist nicht zur Verwendung in Code von Drittanbietern bestimmt, und die Ausnahme darf nicht im Anwendungscode behandelt werden. Stattdessen vermeiden Sie die Ausnahme, indem Sie Einträge zu Ihrer [Laufzeitanweisungsdatei](runtime-directives-rd-xml-configuration-file-reference.md) hinzufügen. Weitere Informationen finden Sie im Abschnitt mit Hinweisen.

## <a name="syntax"></a>Syntax

[!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]

Die Klasse `MissingMetadataException` leitet sich von <xref:System.TypeAccessException> ab.

Die `MissingMetadataException`-Klasse verfügt über die folgenden Member:

## <a name="constructors"></a>Konstruktoren

|Konstruktor|BESCHREIBUNG|
|-----------------|-----------------|
|`public MissingMetadataException()`|Initialisiert eine neue Instanz der `MissingMetadataException`-Klasse mit einer vom System generierten Meldung, die den Fehler beschreibt.<br /><br /> Dieser Konstruktor ist nur für die interne Verwendung durch die .net Native-Toolkette vorgesehen.|
|`public MissingMetadataException(String message)`|Initialisiert eine neue Instanz der `MissingMetadataException`-Klasse mit einer angegebenen Fehlermeldung.<br /><br /> Dieser Konstruktor ist nur für die interne Verwendung durch die .net Native-Toolkette vorgesehen.|

## <a name="properties"></a>Eigenschaften

|Eigenschaft|BESCHREIBUNG|
|--------------|-----------------|
|`public IDictionary Data { get; }`|Ruft eine Auflistung von Schlüssel-Wert-Paaren ab, die zusätzliche benutzerdefinierte Informationen zur Ausnahme bereitstellen. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public string HelpLink { get; set; }`|Ruft einen Link zur Hilfedatei ab, die dieser Ausnahme zugeordnet ist, oder legt einen Link fest. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public int HResult { get; protected set; }`|Ruft `HRESULT`, einen codierten numerischen Wert, der einer bestimmten Ausnahme zugewiesen ist, ab oder legt ihn fest. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public Exception InnerException { get; }`|Ruft die Ausnahme ab, die die aktuelle Ausnahme verursacht hat. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public string Message { get; }`|Ruft eine Meldung ab, mit der die aktuelle Ausnahme beschrieben wird. (Geerbt von <xref:System.TypeLoadException>.)|
|`public string Source { get; set; }`|Ruft den Namen der Anwendung oder des Objekts ab, die bzw. das den Fehler verursacht hat, oder legt den Namen fest. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public string StackTrace { get; }`|Ruft eine Zeichenfolgendarstellung der unmittelbaren Frames in der Aufrufliste ab. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public MethodBase TargetSite { get; }`|Ruft die Methode ab, die die aktuelle Ausnahme ausgelöst hat. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public string TypeName { get; ]`|Ruft den vollqualifizierten Namen des Typs ab, dessen Metadaten fehlen. (Geerbt von <xref:System.TypeLoadException>.)|

## <a name="methods"></a>Methoden

|Methode|Beschreibung|
|------------|-----------------|
|`public bool Equals(Object obj)`|Bestimmt, ob das angegebene Objekt gleich dem aktuellen Objekt ist.  (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`protected void Finalize()`|Gibt einem Objekt Gelegenheit zu dem Versuch, Ressourcen freizugeben und andere Bereinigungen durchzuführen, bevor es von der Garbage Collection freigegeben wird. (Geerbt von <xref:System.Object>.)|
|`public Exception GetBaseException()`|Gibt die Ausnahme zurück, die die Grundursache für eine oder mehrere nachfolgende Ausnahmen ist. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`public int GetHashCode()`|Gibt einen Hashcode für eine `MissingMetadataException`-Instanz zurück.   (Geerbt von <xref:System.Object>.)|
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Legt ein <xref:System.Runtime.Serialization.SerializationInfo>-Objekt mit Informationen über die Ausnahme fest.  (Geerbt von <xref:System.TypeLoadException>.)|
|`public Type GetType()`|Ruft den Laufzeittyp der aktuellen Instanz ab. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|
|`protected Object MemberwiseClone()`|Erstellt eine flache Kopie des aktuellen Objekts. (Geerbt von <xref:System.Object>.)|
|`public string ToString()`|Gibt die Zeichenfolgendarstellung der aktuellen Ausnahme zurück. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|

## <a name="events"></a>Events

|Ereignis|BESCHREIBUNG|
|-----------|-----------------|
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Tritt auf, wenn eine Ausnahme serialisiert wird, um ein Ausnahmezustandsobjekt mit serialisierten Daten über die Ausnahme zu erstellen. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|

## <a name="usage-details"></a>Nutzungsdetails

Die `MissingMetadataException`-Ausnahme wird ausgelöst, wenn Reflektion verwendet wird, um auf Metadaten zuzugreifen, die in einer Assembly nicht verfügbar sind.

Die Metadaten, die einer App zur Laufzeit zur Verfügung stehen, werden durch die laufzeitdirektivendatei (XML-Konfiguration), \* . rd. XML, definiert. Um zu verhindern, dass Ihre App diese Ausnahme auslöst, müssen Sie „\*.rd.xml“ ändern, um die Metadaten zu definieren, die zur Laufzeit vorhanden sein müssen. Informationen zum Format der Datei „\*.rd.xml“ finden Sie unter [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md).

> [!IMPORTANT]
> Da diese Ausnahme anzeigt, dass von der Anwendung benötigte Metadaten zur Laufzeit nicht verfügbar sind, sollten Sie diese Ausnahme nicht in einem `try`/`catch`-Block behandeln. Stattdessen sollten Sie die Ursache der Ausnahme ermitteln und mithilfe einer Laufzeitanweisungsdatei beseitigen. Um den Eintrag zu erhalten, den Sie zur Laufzeitdirektivendatei hinzufügen können, um die Ausnahme zu beseitigen, können Sie eine der beiden Problembehandlungen verwenden:
>
> - Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/type.html) für Typen.
> - Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/method.html) für Methoden.

Die `MissingMetadataException`-Klasse enthält keine eindeutigen Member; alle Member werden von der Basisklasse <xref:System.TypeAccessException> geerbt.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.TypeAccessException>
- [MissingInteropDataException-Klasse](missinginteropdataexception-class-net-native.md)
- [MissingRuntimeArtifactException-Klasse](missingruntimeartifactexception-class-net-native.md)
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
