---
title: MissingRuntimeArtifactException-Klasse (.NET Native)
ms.date: 03/30/2017
ms.assetid: d5b3d13e-689f-4584-8ba6-44f5167a8590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7b138aec8a64683ca4b42cbbc8bd3584c06cc90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397048"
---
# <a name="missingruntimeartifactexception-class-net-native"></a>MissingRuntimeArtifactException-Klasse (.NET Native)
**.NET für Windows-Apps für Windows 10, nur [!INCLUDE[net_native](../../../includes/net-native-md.md)]**  
  
 Die Ausnahme, die ausgelöst wird, wenn Metadaten für einen Typ oder Typmember verfügbar sind, aber dessen Implementierung entfernt wurde.  
  
 **Namespace:** System.Reflection  
  
> [!IMPORTANT]
>  Die `MissingRuntimeArtifactException`-Klasse ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette bestimmt. Sie ist nicht zur Verwendung in Code von Drittanbietern bestimmt, und die Ausnahme darf nicht im Anwendungscode behandelt werden. Stattdessen vermeiden Sie die Ausnahme, indem Sie Einträge zu Ihrer [Laufzeitanweisungsdatei](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
## <a name="syntax"></a>Syntax  
 [!code-csharp[ProjectN#22](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingruntimeartifactexception_syntax1.cs#22)]  
  
 Beachten Sie, dass die `MissingRuntimeArtifactException`-Klasse von <xref:System.MemberAccessException> abgeleitet wird.  
  
 Die `MissingRuntimeArtifactException`-Klasse verfügt über die folgenden Member:  
  
## <a name="constructors"></a>Konstruktoren  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`public MissingRuntimeArtifactException()`|Initialisiert eine neue Instanz der `MissingRuntimeArtifactException`-Klasse mit einer vom System generierten Meldung, die den Fehler beschreibt.<br /><br /> Dieser Konstruktor ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette bestimmt.|  
|`public MissingRuntimeArtifactException(String message)`|Initialisiert eine neue Instanz der `MissingRuntimeArtifactException`-Klasse mit einer angegebenen Fehlermeldung.<br /><br /> Dieser Konstruktor ist nur zur internen Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette bestimmt.|  
  
## <a name="properties"></a>Eigenschaften  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Ruft eine Auflistung von Schlüssel-Wert-Paaren ab, die zusätzliche benutzerdefinierte Informationen über die Ausnahme bereitstellen. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string HelpLink { get; set; }`|Ruft einen Link zu der mit dieser Ausnahme verbundenen Hilfedatei ab oder legt diesen fest. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public int HResult { get; protected set; }`|Ruft `HRESULT`, einen codierten numerischen Wert, der einer bestimmten Ausnahme zugewiesen ist, ab oder legt ihn fest. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public Exception InnerException { get; }`|Ruft die Ausnahme ab, die die aktuelle Ausnahme verursacht hat. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string Message { get; }`|Ruft eine Meldung ab, die die aktuelle Ausnahme beschreibt. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string Source { get; set; }`|Ruft den Namen der Anwendung oder des Objekts ab, die bzw. das den Fehler verursacht hat, oder legt den Namen fest. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string StackTrace { get; }`|Ruft eine Zeichenfolgendarstellung der unmittelbaren Frames in der Aufrufliste ab. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public MethodBase TargetSite { get; }`|Ruft die Methode ab, die die aktuelle Ausnahme ausgelöst hat. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.  (Geerbt von <xref:System.Object>.)|  
|`protected void Finalize()`|Gibt einem Objekt Gelegenheit zu dem Versuch, Ressourcen freizugeben und andere Bereinigungen durchzuführen, bevor es von der Garbage Collection freigegeben wird. (Geerbt von <xref:System.Object>.)|  
|`public Exception GetBaseException()`|Gibt die Ausnahme zurück, die die Ursache für eine oder mehrere nachfolgende Ausnahmen ist. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public int GetHashCode()`|Gibt einen Hashcode für eine `MissingRuntimeArtifactException`-Instanz zurück.   (Geerbt von <xref:System.Object>.)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Legt ein <xref:System.Runtime.Serialization.SerializationInfo>-Objekt mit Informationen über die Ausnahme fest.  (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public Type GetType()`|Ruft den Laufzeittyp der aktuellen Instanz ab. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
|`protected Object MemberwiseClone()`|Erstellt eine flache Kopie des aktuellen Objekts. (Geerbt von <xref:System.Object>.)|  
|`public string ToString()`|Gibt die Zeichenfolgendarstellung der aktuellen Ausnahme zurück. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
  
## <a name="events"></a>Ereignisse  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Tritt auf, wenn eine Ausnahme serialisiert wird, um ein Ausnahmezustandsobjekt mit serialisierten Daten über die Ausnahme zu erstellen. (Geerbt von <xref:System.Exception?displayProperty=nameWithType>.)|  
  
## <a name="usage-details"></a>Details zur Verwendung  
 Die `MissingRuntimeArtifactException`-Ausnahme wird ausgelöst, wenn beim Versuch, einen Typ zu instanziieren oder einen Typmember aufzurufen, zwar die Metadaten des Typs oder Members vorhanden sind, aber die Implementierung entfernt wurde.  
  
 Ob die Metadaten und der Implementierungscode zur dynamischen Ausführung einer Methode für eine App zur Laufzeit verfügbar sind, wird durch die Laufzeitanweisungsdatei "*.rd.xml" (XML-Konfiguration) definiert. Um das Auslösen dieser Ausnahme durch Ihre App zu verhindern, müssen Sie „\*.rd.xml“ so ändern, dass die von einem Typ oder Typmember benötigten Metadaten zur Laufzeit vorhanden sind. Informationen zum Format der Datei „\*.rd.xml“ finden Sie unter [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Da diese Ausnahme anzeigt, dass der von der App benötigte Implementierungscode zur Laufzeit nicht verfügbar ist, sollten Sie diese Ausnahme nicht in einem `try`/`catch`-Block behandeln. Stattdessen sollten Sie die Ursache der Ausnahme ermitteln und mithilfe einer Laufzeitanweisungsdatei beseitigen. In der Regel eliminieren Sie diese Ausnahme durch Angabe der entsprechenden `Activate`- oder `Dynamic`-Richtlinie für ein Programmelement in der Laufzeitdirektivendatei (*.rd.xml-Datei). Um den Eintrag zu erhalten, den Sie zur Laufzeitanweisungsdatei hinzufügen können, um die Ausnahme zu beseitigen, können Sie eine der beiden Problembehandlungen verwenden:  
>   
>  -   Die [MissingMetadataException-Problembehandlung](http://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
> -   Die [MissingMetadataException-Problembehandlung](http://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
 Die `MissingRuntimeArtifactException`-Klasse enthält keine speziellen Elemente. Sie erbt alle Member von ihrer Basisklasse <xref:System.MemberAccessException>.  
  
## <a name="see-also"></a>Siehe auch  
 [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
