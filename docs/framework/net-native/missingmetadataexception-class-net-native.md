---
title: "MissingMetadataException-Klasse (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 408f25c4-6d60-475c-92b1-7b52b777c6db
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# MissingMetadataException-Klasse (.NET Native)
**.NET für Windows\-Apps für Windows 10, nur [!INCLUDE[net_native](../../../includes/net-native-md.md)]**  
  
 Die Ausnahme, die ausgelöst wird, wenn Reflektion verwendet wird, um Metadaten abzurufen, die nicht vorhanden sind.  
  
 **Namespace:** System.Reflection  
  
> [!IMPORTANT]
>  Die `MissingMetadataException`\-Klasse ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Toolkette bestimmt.  Sie ist nicht zur Verwendung in Code von Drittanbietern bestimmt, und die Ausnahme darf nicht im Anwendungscode behandelt werden.  Stattdessen vermeiden Sie die Ausnahme, indem Sie Einträge in Ihrer [Laufzeitdirektivendatei](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) hinzufügen.  Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
## Syntax  
 [!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]  
  
 Beachten Sie, dass die `MissingMetadataException`\-Klasse von <xref:System.TypeAccessException> abgeleitet wird.  
  
 Die `MissingMetadataException`\-Klasse verfügt über die folgenden Member:  
  
## Konstruktoren  
  
|Konstruktor|Beschreibung|  
|-----------------|------------------|  
|`public MissingMetadataException()`|Initialisiert eine neue Instanz der `MissingMetadataException`\-Klasse mit einer vom System generierten Meldung, die den Fehler beschreibt.<br /><br /> Dieser Konstruktor ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Toolkette bestimmt.|  
|`public MissingMetadataException(String message)`|Initialisiert eine neue Instanz der `MissingMetadataException`\-Klasse mit einer angegebenen Fehlermeldung.<br /><br /> Dieser Konstruktor ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Torolkette bestimmt.|  
  
## Eigenschaften  
  
|Eigenschaft|Beschreibung|  
|-----------------|------------------|  
|`public IDictionary Data { get; }`|Ruft eine Auflistung von Schlüssel\-Wert\-Paaren ab, die zusätzliche benutzerdefinierte Informationen über die Ausnahme bereitstellen.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string HelpLink { get; set; }`|Ruft einen Link zur Hilfedatei ab, die dieser Ausnahme zugeordnet ist, oder legt einen Link fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public int HResult { get; protected set; }`|Ruft `HRESULT`, einen codierten numerischen Wert, der einer bestimmten Ausnahme zugewiesen ist, ab oder legt ihn fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public Exception InnerException { get; }`|Ruft die Ausnahme ab, die die aktuelle Ausnahme verursacht hat.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string Message { get; }`|Ruft eine Meldung ab, die die aktuelle Ausnahme beschreibt.  \(Geerbt von <xref:System.TypeLoadException>.\)|  
|`public string Source { get; set; }`|Ruft den Namen der Anwendung oder des Objekts ab, die bzw. das den Fehler verursacht hat, oder legt den Namen fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string StackTrace { get; }`|Ruft eine Zeichenfolgendarstellung der unmittelbaren Frames in der Aufrufliste ab.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public MethodBase TargetSite { get; }`|Ruft die Methode ab, die die aktuelle Ausnahme ausgelöst hat.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string TypeName { get; ]`|Ruft den vollqualifizierten Namen des Typs ab, dessen Metadaten fehlen.  \(Geerbt von <xref:System.TypeLoadException>.\)|  
  
## Methoden  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|`public bool Equals(Object obj)`|Bestimmt, ob das angegebene Objekt dem aktuellen Objekt entspricht.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`protected void Finalize()`|Gibt einem Objekt Gelegenheit zu dem Versuch, Ressourcen freizugeben und andere Bereinigungen durchzuführen, bevor es von der Garbage Collection freigegeben wird.  \(Geerbt von <xref:System.Object>.\)|  
|`public Exception GetBaseException()`|Gibt die Ausnahme zurück, die die Ursache für eine oder mehrere nachfolgende Ausnahmen ist.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public int GetHashCode()`|Gibt einen Hashcode für eine `MissingMetadataException`\-Instanz zurück.  \(Geerbt von <xref:System.Object>.\)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Legt ein <xref:System.Runtime.Serialization.SerializationInfo>\-Objekt mit Informationen über die Ausnahme fest.  \(Geerbt von <xref:System.TypeLoadException>.\)|  
|`public Type GetType()`|Ruft den Laufzeittyp der aktuellen Instanz ab.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`protected Object MemberwiseClone()`|Erstellt eine flache Kopie des aktuellen Objekts.  \(Geerbt von <xref:System.Object>.\)|  
|`public string ToString()`|Gibt die Zeichenfolgendarstellung der aktuellen Ausnahme zurück.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
  
## Ereignisse  
  
|Ereignis|Beschreibung|  
|--------------|------------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Tritt auf, wenn eine Ausnahme serialisiert wird, um ein Ausnahmezustandsobjekt zu erstellen, das serialisierte Daten für die Ausnahme enthält.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
  
## Details zur Verwendung  
 Die `MissingMetadataException`\-Ausnahme wird ausgelöst, wenn Reflektion verwendet wird, um auf Metadaten zuzugreifen, die in einer Assembly nicht verfügbar sind.  
  
 Die Metadaten, die einer App zur Laufzeit zur Verfügung stehen, werden durch die Laufzeitdirektivendatei \(XML\-Konfiguration\) \*.rd.xml definiert.  Um zu verhindern, dass Ihre App diese Ausnahme auslöst, müssen Sie "\*.rd.xml" ändern, um die Metadaten zu definieren, die zur Laufzeit vorhanden sein müssen.  Informationen zum Format der Datei "\*.rd.xml" finden Sie unter [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Da diese Ausnahme anzeigt, dass von der Anwendung benötigte Metadaten zur Laufzeit nicht verfügbar sind, sollten Sie diese Ausnahme nicht in einem `try`\/`catch`\-Block behandeln.  Stattdessen sollten Sie die Ursache der Ausnahme ermitteln und mithilfe einer Laufzeitdirektivendatei beseitigen.  Um den Eintrag zu erhalten, den Sie zur Laufzeitdirektivendatei hinzufügen können, um die Ausnahme zu beseitigen, können Sie eine der beiden Problembehandlungen verwenden:  
>   
>  -   Die [MissingMetadataException\-Problembehandlung](http://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
> -   Die [MissingMetadataException\-Problembehandlung](http://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
 Die `MissingMetadataException`\-Klasse enthält keine speziellen Elemente. Sie erbt alle Member von ihrer Basisklasse <xref:System.TypeAccessException>.  
  
## Siehe auch  
 <xref:System.Exception?displayProperty=fullName>   
 <xref:System.TypeAccessException>   
 [MissingInteropDataException\-Klasse](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)   
 [MissingRuntimeArtifactException\-Klasse](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)   
 [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)