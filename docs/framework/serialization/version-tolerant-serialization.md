---
title: "Versionstolerante Serialisierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "BinaryFormatter-Klasse, Beispiele"
  - "Serialisierung, Attribute"
  - "Serialisierung, Kontrollieren"
  - "Serialisierung, Benutzerdefinierte Serialisierung"
  - "Serialisierung, Versionstolerant"
  - "Versionstolerante Serialisierung"
  - "Versionen und Serialisierung"
ms.assetid: bea0ffe3-2708-4a16-ac7d-e586ed6b8e8d
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Versionstolerante Serialisierung
In Version 1.0 und Version 1.1 von .NET Framework war das Erstellen serialisierbarer Typen, die für mehrere Anwendungsversionen verwendbar waren, problematisch.Wenn ein Typ durch Hinzufügen eines zusätzlicher Felder geändert wurde, traten die folgenden Probleme auf:  
  
-   Ältere Versionen einer Anwendung lösten bei dem Versuch, neue Versionen des alten Typs zu deserialisieren, Ausnahmen aus.  
  
-   Neuere Versionen einer Anwendung lösten bei dem Versuch, ältere Versionen eines Typs mit fehlenden Daten zu deserialisieren, Ausnahmen aus.  
  
 Bei VTS \(Version Tolerant Serialization\) handelt es sich um eine Gruppe von Funktionen, die in .NET Framework 2.0 eingeführt wurde, um das möglicherweise im Laufe der Zeit erforderliche Ändern serialisierbarer Typen zu vereinfachen.Die VTS\-Funktionen sind insbesondere für Klassen aktiviert, auf die das <xref:System.SerializableAttribute>\-Attribut angewendet wurde, einschließlich generischer Typen.VTS ermöglicht das Hinzufügen neuer Felder zu diesen Klassen, ohne die Kompatibilität mit anderen Versionen des Typs zu beeinträchtigen.Eine funktionierende Beispielanwendung finden Sie unter [Technologiebeispiel für versionstolerante Serialisierung](../../../docs/framework/serialization/version-tolerant-serialization-technology-sample.md).  
  
 Die VTS\-Funktionen werden bei der Verwendung von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> aktiviert.Zudem sind alle Funktionen mit Ausnahme der Toleranz für externe Daten auch bei der Verwendung von <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> aktiviert.Weitere Informationen zur Verwendung dieser Klassen für die Serialisierung finden Sie unter [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md).  
  
## Funktionsliste  
 VTS umfasst die folgenden Funktionen:  
  
-   Toleranz für externe oder unerwartete Daten.Dies ermöglicht es neueren Versionen des Typs, Daten an frühere Versionen zu senden.  
  
-   Toleranz für fehlende optionale Daten.Dies ermöglicht es älteren Versionen, Daten an neuere Versionen zu senden.  
  
-   Serialisierungsrückrufe.Dies ermöglicht ein intelligentes Festlegen von Standardwerten im Fall fehlender Daten.  
  
 Zudem ist eine Funktion zum Deklarieren verfügbar, wenn ein neues optionales Feld hinzugefügt wurde.Es handelt sich hierbei um die <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>\-Eigenschaft des <xref:System.Runtime.Serialization.OptionalFieldAttribute>\-Attributs.  
  
 Diese Funktionen werden nachfolgend näher erläutert.  
  
## Toleranz für externe oder unerwartete Daten  
 In früheren Versionen wurden während der Deserialisierung bei auftretenden externen oder unerwarteten Daten Ausnahmen.Mit VTS werden in derselben Situation keine Ausnahmen mehr ausgelöst, sondern alle externen oder unerwarteten Daten werden ignoriert.Dies ermöglicht es, Anwendungen mit neueren Versionen eines Typs \(d. h. eine Version mit mehr Feldern\), Informationen an Anwendungen zu senden, die ältere Versionen desselben Typs erwarten.  
  
 Im folgenden Beispiel werden die zusätzlichen Daten im `CountryField`\-Feld von Version 2.0 der `Address`\-Klasse ignoriert, wenn eine ältere Anwendung die neuere Version deserialisiert.  
  
```csharp  
// Version 1 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
}  
// Version 2.0 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    // The older application ignores this data.  
    public string CountryField;  
}  
```  
  
```vb  
' Version 1 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
End Class  
  
' Version 2.0 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    ' The older application ignores this data.  
    Public CountryField As String  
End Class  
```  
  
## Toleranz für fehlende Daten  
 Felder können mithilfe des <xref:System.Runtime.Serialization.OptionalFieldAttribute>\-Attributs als optional markiert werden.Wenn während der Deserialisierung optionale Daten fehlen, ignoriert das Serialisierungsmodul das Fehlen dieser Daten und löst keine Ausnahme aus.Anwendungen, die ältere Versionen eines Typs erwarten, können daher Daten an Anwendungen senden, die neuere Versionen desselben Typs erwarten.  
  
 Im folgenden Beispiel wird Version 2.0 der `Address`\-Klasse mit dem als optional markierten `CountryField`\-Feld veranschaulicht.Wenn eine ältere Anwendung Version 1 an eine neuere Anwendung sendet, die Version 2.0 erwartet, wird das Fehlen der Daten ignoriert.  
  
```csharp  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
  
    [OptionalField]  
    public string CountryField;  
}  
```  
  
```vb  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
  
    <OptionalField> _  
    Public CountryField As String  
End Class  
```  
  
## Serialisierungsrückrufe  
 Serialisierungsrückrufe stellen einen Mechanismus dar, der an vier Punkten im Serialisierungs\-\/Deserialisierungsprozess Hooks bereitstellt.  
  
|Attribut|Beim Aufruf der verknüpften Methode|Typische Verwendung|  
|--------------|-----------------------------------------|-------------------------|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Vor der Deserialisierung. \*|Initialisieren von Standardwerten für optionale Felder.|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Nach der Deserialisierung.|Korrigieren Sie optionale Feldwerte auf der Grundlage des Inhalts anderer Felder.|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Vor der Deserialisierung.|Vorbereiten der Serialisierung.Erstellen Sie z. B. optionale Datenstrukturen.|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Nach der Serialisierung.|Protokollieren der Serialisierungsereignisse.|  
  
 \* Dieser Rückruf wird vor dem Deserialisierungskonstruktor aufgerufen, sofern ein solcher vorhanden ist.  
  
### Verwenden von Rückrufen  
 Zur Verwendung von Rückrufen wenden Sie die entsprechenden Attribute auf eine Methode an, die einen <xref:System.Runtime.Serialization.StreamingContext>\-Parameter akzeptiert.Mit jedem dieser Attribute kann nur eine Methode pro Klasse markiert werden.Beispiel:  
  
```csharp  
[OnDeserializing]  
private void SetCountryRegionDefault(StreamingContext sc)  
{  
    CountryField = "Japan";  
}  
  
```  
  
```vb  
<OnDeserializing>  
Private Sub SetCountryRegionDefault(StreamingContext sc)  
    CountryField = "Japan";  
End Sub  
```  
  
 Diese Methoden sind für die Versionsverwaltung vorgesehen.Während der Deserialisierung wird ein optionales Feld möglicherweise nicht korrekt initialisiert, wenn die Daten für das Feld fehlen.Dies kann korrigiert werden, indem zunächst die Methode erstellt wird, die den richtigen Wert zuordnet, und dann entweder das **OnDeserializingAttribute**\-Attribut oder das **OnDeserializedAttribute**\-Attribut auf die Methode anwendet wird.  
  
 Im folgenden Beispiel wird die Methode im Kontext eines Typs veranschaulicht.Wenn eine frühere Version einer Anwendung eine Instanz der  `Address`\-Klasse an eine höhere Version der Anwendung sendet, fehlen Daten im `CountryField`\-Feld.Nach der Deserialisierung wird das Feld jedoch auf den Standardwert "Japan" festgelegt.  
  
```csharp  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    [OptionalField]  
    public string CountryField;  
  
    [OnDeserializing]  
    private void SetCountryRegionDefault (StreamingContext sc)  
    {  
        CountryField = "Japan";  
    }  
}  
  
```  
  
```vb  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    <OptionalField> _  
    Public CountryField As String  
  
    <OnDeserializing> _  
    Private Sub SetCountryRegionDefault(StreamingContext sc)  
        CountryField = "Japan";  
    End Sub  
End Class  
```  
  
## Die VersionAdded\-Eigenschaft  
 Das **OptionalFieldAttribute**\-Objekt verfügt über die **VersionAdded**\-Eigenschaft.In Version 2.0 von .NET Framework wird diese nicht verwendet.Es ist jedoch wichtig, dass diese Eigenschaft richtig festgelegt wird, um sicherzustellen, dass der Typ mit zukünftigen Serialisierungmodulen kompatibel ist.  
  
 Die Eigenschaft gibt an, welche Version eines Typs einem bestimmten Feld hinzugefügt wurde.Sie sollte bei jeder Änderung des Typs um genau 1 erhöht werden \(ausgehend von 2\). Dies veranschaulicht das folgende Beispiel:  
  
```csharp  
// Version 1.0  
[Serializable]  
public class Person  
{  
    public string FullName;  
}  
  
// Version 2.0  
[Serializable]  
public class Person  
{  
    public string FullName;  
  
    [OptionalField(VersionAdded = 2)]  
    public string NickName;  
    [OptionalField(VersionAdded = 2)]  
    public DateTime BirthDate;  
}  
  
// Version 3.0  
[Serializable]  
public class Person  
{  
    public string FullName;  
  
    [OptionalField(VersionAdded=2)]  
    public string NickName;  
    [OptionalField(VersionAdded=2)]  
    public DateTime BirthDate;  
  
    [OptionalField(VersionAdded=3)]  
    public int Weight;  
}  
```  
  
```vb  
' Version 1.0  
<Serializable> _  
Public Class Person  
    Public FullName  
End Class  
  
' Version 2.0  
<Serializable> _  
Public Class Person  
    Public FullName As String  
  
    <OptionalField(VersionAdded := 2)> _  
    Public NickName As String  
    <OptionalField(VersionAdded := 2)> _  
    Public BirthDate As DateTime  
End Class  
  
' Version 3.0  
<Serializable> _  
Public Class Person  
    Public FullName As String  
  
    <OptionalField(VersionAdded := 2)> _  
    Public NickName As String  
    <OptionalField(VersionAdded := 2)> _  
    Public BirthDate As DateTime  
  
    <OptionalField(VersionAdded := 3)> _  
    Public Weight As Integer  
End Class  
```  
  
## SerializationBinder  
 Einige Benutzer müssen möglicherweise steuern, welche Klasse serialisiert und deserialisiert werden soll, da eine andere Version der Klasse auf dem Server und Client erforderlich ist.<xref:System.RuntimeSerialization.SerializationBinder> ist eine abstrakte Klasse, mit der die tatsächlichen Typen gesteuert werden, die während der Serialisierung und Deserialisierung verwendet werden.Um diese Klasse zu verwenden, leiten Sie eine Klasse von <xref:System.RuntimeSerialization.SerializationBinder> ab und überschreiben die <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False&autoUpgrade=True\-Methode und <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False&autoUpgrade=True\-Methode.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Steuern der Serialisierung und Deserialisierung mit SerializationBinder](../../../docs/framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).  
  
## Bewährte Methoden  
 Um das richtige Versionsverhalten sicherzustellen, beachten Sie beim Ändern eines Typs von Version zu Version die folgenden Regeln:  
  
-   Entfernen Sie nie ein serialisiertes Feld.  
  
-   Wenden Sie das <xref:System.NonSerializedAttribute>\-Attribut nie auf ein Feld an, wenn das Attribut in der vorherigen Version nicht auf das Feld angewendet wurde.  
  
-   Ändern Sie nie den Namen oder den Typ eines serialisierten Felds.  
  
-   Wenden Sie beim Hinzufügen eines neuen serialisierten Felds das **OptionalFieldAttribute**\-Attribut an.  
  
-   Wenden Sie beim Entfernen eines **NonSerializedAttribute**\-Attributs von einem Feld, das in einer vorherigen Version nicht serialisierbar war, das **OptionalFieldAttribute**\-Attribut an.  
  
-   Legen Sie für alle optionalen Felder sinnvolle Standardwerte fest, indem Sie die Serialisierungsrückrufe verwenden, sofern 0 oder **null** nicht als Standardwerte zulässig sind.  
  
 Um sicherzustellen, dass ein Typ mit zukünftigen Serialisierungsmodulen kompatibel ist, beachten Sie die folgenden Richtlinien:  
  
-   Legen Sie die **VersionAdded**\-Eigenschaft für das **OptionalFieldAttribute**\-Attribut immer richtig fest.  
  
-   Vermeiden Sie verzweigte Versionen.  
  
## Siehe auch  
 <xref:System.SerializableAttribute>   
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>   
 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>   
 <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>   
 <xref:System.Runtime.Serialization.OptionalFieldAttribute>   
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>   
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>   
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>   
 <xref:System.Runtime.Serialization.OnSerializedAttribute>   
 <xref:System.Runtime.Serialization.StreamingContext>   
 <xref:System.NonSerializedAttribute>   
 [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md)