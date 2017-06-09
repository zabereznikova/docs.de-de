---
title: "MissingInteropDataException-Klasse (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# MissingInteropDataException-Klasse (.NET Native)
**.NET für Windows\-Apps für Windows 10, nur [!INCLUDE[net_native](../../../includes/net-native-md.md)]**  
  
 Die Ausnahme, die ausgelöst wird, wenn eine manuelle Marshallingmethode aufgerufen wird, aber keine Metadaten für einen Typ durch statische Analyse oder in einer Laufzeitrichtliniendatei gefunden werden.  
  
 **Namespace:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
>  Die `MissingInteropDataException`\-Klasse ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Toolkette bestimmt.  Sie ist nicht zur Verwendung in Code von Drittanbietern bestimmt, und die Ausnahme darf nicht im Anwendungscode behandelt werden.  Stattdessen vermeiden Sie die Ausnahme, indem Sie Einträge in Ihrer [Laufzeitdirektivendatei](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) hinzufügen.  Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
## Syntax  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 Die `MissingInteropDataException`\-Klasse verfügt über die folgenden Member:  
  
## Konstruktoren  
  
|Konstruktor|Beschreibung|  
|-----------------|------------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Initialisiert eine neue Instanz der `MissingInteropDataException`\-Klasse mit der ID einer vom System generierten Meldung, die den Fehler und den Typ, dessen Daten fehlen, beschreibt.  Dieser Konstruktor ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]\-Toolkette bestimmt.|  
  
## Eigenschaften  
  
|Eigenschaft|Beschreibung|  
|-----------------|------------------|  
|`public IDictionary Data { get; }`|Ruft eine Auflistung von Schlüssel\-Wert\-Paaren ab, die zusätzliche benutzerdefinierte Informationen über die Ausnahme bereitstellen.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string HelpLink { get; set; }`|Ruft einen Link zur Hilfedatei ab, die dieser Ausnahme zugeordnet ist, oder legt einen Link fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public int HResult { get; protected set; }`|Ruft `HRESULT`, einen codierten numerischen Wert, der einer bestimmten Ausnahme zugewiesen ist, ab oder legt ihn fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public Exception InnerException { get; }`|Ruft die Ausnahme ab, die die aktuelle Ausnahme verursacht hat.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string Message { get; }`|Ruft eine Meldung ab, die die aktuelle Ausnahme beschreibt.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public Type MissingType { get; private set; }`|Ruft den Typ, dessen Daten fehlen, ab oder legt ihn fest.|  
|`public string Source { get; set; }`|Ruft den Namen der App oder des Objekts ab, die bzw. das den Fehler verursacht hat, oder legt den Namen fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public string StackTrace { get; }`|Ruft eine Zeichenfolgendarstellung der unmittelbaren Frames in der Aufrufliste ab.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public MethodBase TargetSite { get; }`|Ruft die Methode ab, die die aktuelle Ausnahme ausgelöst hat.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
  
## Methoden  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|`public bool Equals(Object obj)`|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.  \(Geerbt von <xref:System.Object>.\)|  
|`protected void Finalize()`|Gibt einem Objekt Gelegenheit zu dem Versuch, Ressourcen freizugeben und andere Bereinigungen durchzuführen, bevor es von der Garbage Collection freigegeben wird.  \(Geerbt von <xref:System.Object>.\)|  
|`public Exception GetBaseException()`|Gibt die Ausnahme zurück, die die Ursache für eine oder mehrere nachfolgende Ausnahmen ist.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public int GetHashCode()`|Gibt einen Hashcode für eine `MissingInteropDataException`\-Instanz zurück.  \(Geerbt von <xref:System.Object>.\)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Legt ein <xref:System.Runtime.Serialization.SerializationInfo>\-Objekt mit Informationen über die Ausnahme fest.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`public Type GetType()`|Ruft den Laufzeittyp der aktuellen Instanz ab.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
|`protected Object MemberwiseClone()`|Erstellt eine flache Kopie des aktuellen Objekts.  \(Geerbt von <xref:System.Object>.\)|  
|`public string ToString()`|Gibt die Zeichenfolgendarstellung der aktuellen Ausnahme zurück.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
  
## Ereignisse  
  
|Ereignis|Beschreibung|  
|--------------|------------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Tritt auf, wenn eine Ausnahme serialisiert wird, um ein Ausnahmezustandsobjekt zu erstellen, das serialisierte Daten für die Ausnahme enthält.  \(Geerbt von <xref:System.Exception?displayProperty=fullName>.\)|  
  
## Details zur Verwendung  
 Die `MissingInteropDataException`\-Ausnahme wird ausgelöst, wenn ein Methodenaufruf an eine COM\- oder Windows\-Runtime\-Komponente nicht erfolgreich ausgeführt werden kann, weil Typinformationen nicht zur Verfügung stehen.  
  
 Die Metadaten, die einer App zur Laufzeit zur Verfügung stehen, werden durch die Laufzeitdirektivendatei \(XML\-Konfiguration\) \*.rd.xml definiert.  Um das Auslösen dieser Ausnahme durch die App zu verhindern, müssen Sie diese Datei ändern und die Metadaten definieren, die zur Laufzeit vorhanden sein müssen.  In den meisten Fällen beheben Sie diesen Fehler, indem Sie einem geeigneten Programmelement in der Laufzeitdirektivendatei ein `MarshalObject`\-, `MarshalDelegate`\- oder `MarshalStructure`\-Attribut hinzufügen.  Informationen zum Format dieser Datei finden Sie unter [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Da diese Ausnahme anzeigt, dass von der Anwendung benötigte Metadaten zur Laufzeit nicht verfügbar sind, sollten Sie diese Ausnahme nicht in einem `try`\/`catch`\-Block behandeln.  Stattdessen sollten Sie die Ursache der Ausnahme ermitteln und durch Hinzufügen des entsprechenden Eintrags zu einer Laufzeitdirektivendatei beseitigen.  
  
 Die `MissingInteropDataException`\-Klasse enthält einen einzelnen eindeutigen Member, die `MissingType`\-Eigenschaft, die den Typ angibt, dessen Metadaten für einen erfolgreichen Aufruf benötigt werden.  Alle anderen Eigenschaften werden von der Basisklasse <xref:System.Exception?displayProperty=fullName> geerbt.  
  
## Siehe auch  
 <xref:System.Exception?displayProperty=fullName>   
 [MissingMetadataException\-Klasse](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)   
 [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)