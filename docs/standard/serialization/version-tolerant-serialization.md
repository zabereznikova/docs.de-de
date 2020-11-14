---
title: Versionstolerante Serialisierung
description: Erfahren Sie mehr zur versionstoleranten Serialisierung, einer Gruppe von Funktionen, die das Ändern serialisierbarer Typen vereinfachen.
ms.date: 08/08/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- version tolerant serialization
- serialization, custom serialization
- serialization, version tolerant
- serialization, controlling
- versions and serialization
- BinaryFormatter class, samples
- serialization, attributes
ms.assetid: bea0ffe3-2708-4a16-ac7d-e586ed6b8e8d
ms.openlocfilehash: e7c4d6ca4c72390c3e0803502aa9c1a675e02345
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282414"
---
# <a name="version-tolerant-serialization"></a>Versionstolerante Serialisierung

In den ersten Versionen von .NET Framework war das Erstellen serialisierbarer Typen problematisch, die für mehrere Anwendungsversionen wiederverwendbar waren. Wenn ein Typ durch Hinzufügen eines zusätzlicher Felder geändert wurde, traten die folgenden Probleme auf:

- Ältere Versionen einer Anwendung lösten bei dem Versuch, neue Versionen des alten Typs zu deserialisieren, Ausnahmen aus.
- Neuere Versionen einer Anwendung lösten bei dem Versuch, ältere Versionen eines Typs mit fehlenden Daten zu deserialisieren, Ausnahmen aus.

Bei VTS (Version Tolerant Serialization, versionstolerante Serialisierung) handelt es sich um eine Gruppe von Funktionen, die das möglicherweise im Laufe der Zeit erforderliche Ändern serialisierbarer Typen vereinfachen. Die VTS-Funktionen sind insbesondere für Klassen aktiviert, auf die das <xref:System.SerializableAttribute>-Attribut angewendet wurde, einschließlich generischer Typen. VTS ermöglicht das Hinzufügen neuer Felder zu diesen Klassen, ohne die Kompatibilität mit anderen Versionen des Typs zu beeinträchtigen. Informationen zu einer funktionierenden Beispielanwendung finden Sie unter [Technologiebeispiel für versionstolerante Serialisierung](basic-serialization-technology-sample.md).

Die VTS-Funktionen werden bei der Verwendung von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> aktiviert. Zudem sind alle Funktionen mit Ausnahme der Toleranz für externe Daten auch bei der Verwendung von <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> aktiviert. Weitere Informationen zur Verwendung dieser Klassen für die Serialisierung finden Sie unter [Binäre Serialisierung](binary-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a>Funktionsliste

VTS umfasst die folgenden Funktionen:

- Toleranz für externe oder unerwartete Daten. Dies ermöglicht es neueren Versionen des Typs, Daten an frühere Versionen zu senden.
- Toleranz für fehlende optionale Daten. Dies ermöglicht es älteren Versionen, Daten an neuere Versionen zu senden.
- Serialisierungsrückrufe. Dies ermöglicht ein intelligentes Festlegen von Standardwerten im Fall fehlender Daten.

Zudem ist eine Funktion zum Deklarieren verfügbar, wenn ein neues optionales Feld hinzugefügt wurde. Es handelt sich hierbei um die <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>-Eigenschaft des <xref:System.Runtime.Serialization.OptionalFieldAttribute>-Attributs.

Diese Funktionen werden in den folgenden Abschnitten ausführlicher erläutert.

### <a name="tolerance-of-extraneous-or-unexpected-data"></a>Toleranz für externe oder unerwartete Daten

In früheren Versionen wurden während der Deserialisierung bei auftretenden externen oder unerwarteten Daten Ausnahmen. Mit VTS werden in derselben Situation keine Ausnahmen mehr ausgelöst, sondern alle externen oder unerwarteten Daten werden ignoriert. Dies ermöglicht es, Anwendungen mit neueren Versionen eines Typs (d.&#160;h. eine Version mit mehr Feldern), Informationen an Anwendungen zu senden, die ältere Versionen desselben Typs erwarten.

Im folgenden Beispiel werden die zusätzlichen Daten im `CountryField`-Feld von Version&#160;2.0 der `Address`-Klasse ignoriert, wenn eine ältere Anwendung die neuere Version deserialisiert.

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

### <a name="tolerance-of-missing-data"></a>Toleranz für fehlende Daten

Felder können mithilfe des <xref:System.Runtime.Serialization.OptionalFieldAttribute>-Attributs als optional markiert werden. Wenn während der Deserialisierung optionale Daten fehlen, ignoriert die Serialisierungs-Engine das Fehlen dieser Daten und löst keine Ausnahme aus. Anwendungen, die ältere Versionen eines Typs erwarten, können daher Daten an Anwendungen senden, die neuere Versionen desselben Typs erwarten.

Im folgenden Beispiel wird Version&#160;2.0 der `Address`-Klasse mit dem als optional markierten `CountryField`-Feld veranschaulicht. Wenn eine ältere Anwendung Version&#160;1 an eine neuere Anwendung sendet, die Version&#160;2.0 erwartet, wird das Fehlen der Daten ignoriert.

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
  
### <a name="serialization-callbacks"></a>Serialisierungsrückrufe

Serialisierungsrückrufe stellen einen Mechanismus dar, der an vier Punkten im Serialisierungs-/Deserialisierungsprozess Hooks bereitstellt.

|Attribut|Beim Aufruf der verknüpften Methode|Typische Verwendung|
|---------------|------------------------------------------|-----------------|
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Vor der Deserialisierung.\*|Initialisieren von Standardwerten für optionale Felder.|
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Nach der Deserialisierung.|Korrigieren Sie optionale Feldwerte auf der Grundlage des Inhalts anderer Felder.|
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Vor der Deserialisierung.|Vorbereiten der Serialisierung. Erstellen Sie z.&#160;B. optionale Datenstrukturen.|
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Nach der Serialisierung.|Protokollieren der Serialisierungsereignisse.|

 \* Dieser Rückruf wird vor dem Deserialisierungskonstruktor aufgerufen, sofern ein solcher vorhanden ist.

#### <a name="using-callbacks"></a>Verwenden von Rückrufen

Zur Verwendung von Rückrufen wenden Sie die entsprechenden Attribute auf eine Methode an, die einen <xref:System.Runtime.Serialization.StreamingContext>-Parameter akzeptiert. Mit jedem dieser Attribute kann nur eine Methode pro Klasse markiert werden. Zum Beispiel:

```csharp
[OnDeserializing]
private void SetCountryRegionDefault(StreamingContext sc)
{
    CountryField = "Japan";
}
```

```vb
<OnDeserializing>
Private Sub SetCountryRegionDefault(sc As StreamingContext)
    CountryField = "Japan"
End Sub
```

Diese Methoden sind für die Versionsverwaltung vorgesehen. Während der Deserialisierung wird ein optionales Feld möglicherweise nicht korrekt initialisiert, wenn die Daten für das Feld fehlen. Dies kann korrigiert werden, indem zunächst die Methode erstellt wird, die den richtigen Wert zuordnet, und dann entweder das **OnDeserializingAttribute** - oder **OnDeserializedAttribute** -Attribut auf die Methode angewendet wird.

Im folgenden Beispiel wird die Methode im Kontext eines Typs veranschaulicht. Wenn eine frühere Version einer Anwendung eine Instanz der`Address`-Klasse an eine höhere Version der Anwendung sendet, fehlen Daten im `CountryField`-Feld. Nach der Deserialisierung wird das Feld jedoch auf den Standardwert „Japan“ festgelegt.

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;
    [OptionalField]
    public string CountryField;

    [OnDeserializing]
    private void SetCountryRegionDefault(StreamingContext sc)
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
    Private Sub SetCountryRegionDefault(sc As StreamingContext)
        CountryField = "Japan"
    End Sub
End Class
```

## <a name="the-versionadded-property"></a>Die VersionAdded-Eigenschaft

Das **OptionalFieldAttribute** verfügt über die **VersionAdded** -Eigenschaft. Die Eigenschaft gibt an, welche Version eines Typs einem bestimmten Feld hinzugefügt wurde. Sie sollte bei jeder Änderung des Typs um genau 1 erhöht werden (ausgehend von 2). Dies veranschaulicht das folgende Beispiel:

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

## <a name="serializationbinder"></a>SerializationBinder

Einige Benutzer müssen möglicherweise steuern, welche Klasse serialisiert und deserialisiert werden soll, da unterschiedliche Versionen der Klasse auf dem Server und Client erforderlich ist. <xref:System.Runtime.Serialization.SerializationBinder> ist eine abstrakte Klasse, mit der die tatsächlichen Typen gesteuert werden, die während der Serialisierung und Deserialisierung verwendet werden. Wenn Sie diese Klasse verwenden möchten, müssen Sie eine Klasse von <xref:System.Runtime.Serialization.SerializationBinder> ableiten und die <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A>-Methode und die <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>-Methode überschreiben. Weitere Informationen finden Sie unter [Steuern der Serialisierung und Deserialisierung mit SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).

## <a name="best-practices"></a>Bewährte Methoden

Um das richtige Versionsverhalten sicherzustellen, beachten Sie beim Ändern eines Typs von Version zu Version die folgenden Regeln:

- Entfernen Sie nie ein serialisiertes Feld.
- Wenden Sie das <xref:System.NonSerializedAttribute>-Attribut nie auf ein Feld an, wenn das Attribut in der vorherigen Version nicht auf das Feld angewendet wurde.
- Ändern Sie nie den Namen oder den Typ eines serialisierten Felds.
- Wenden Sie beim Hinzufügen eines neuen serialisierten Felds das **OptionalFieldAttribute** -Attribut an.
- Wenden Sie beim Entfernen eines **NonSerializedAttribute** -Attributs von einem Feld, das in einer vorherigen Version nicht serialisierbar war, das **OptionalFieldAttribute** -Attribut an.
- Legen Sie für alle optionalen Felder sinnvolle Standardwerte fest, indem Sie die Serialisierungsrückrufe verwenden, sofern 0 oder **NULL** nicht als Standardwerte zulässig sind.

Um sicherzustellen, dass ein Typ mit zukünftigen Serialisierungs-Engines kompatibel ist, beachten Sie die folgenden Richtlinien:

- Legen Sie die **VersionAdded** -Eigenschaft im **OptionalFieldAttribute** -Attribut ordnungsgemäß fest.
- Vermeiden Sie verzweigte Versionen.

## <a name="see-also"></a>Siehe auch

- <xref:System.SerializableAttribute>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- <xref:System.NonSerializedAttribute>
- [Binäre Serialisierung](binary-serialization.md)
