---
title: Benutzerdefinierte Serialisierung
description: Die benutzerdefinierte Serialisierung ist die Steuerung der Serialisierung und Deserialisierung eines Typs. Das Steuern der Serialisierung kann die Serialisierungskompatibilität sicherstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binary serialization, custom serialization
- custom serialization
- binary serialization, controlling
- OptionalFieldAttribute class, custom serialization
- ISerializable interface, custom serialization
- OnDeserializingAttribute class, custom serialization
- OnSerializedAttribute class, custom serialization
- serialization, custom serialization
- serialization, controlling
- OnDeserializedAttribute class, custom serialization
- OnSerializingAttribute class, custom serialization
ms.assetid: 12ed422d-5280-49b8-9b71-a2ed129c0384
ms.openlocfilehash: 8e8d8d38ab8170a9bf9fae098e267be1a38f27d0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281786"
---
# <a name="custom-serialization"></a>Benutzerdefinierte Serialisierung

Unter benutzerdefinierter Serialisierung wird die Steuerung der Serialisierung und Deserialisierung eines Typs verstanden. Durch die Steuerung der Serialisierung lässt sich die Serialisierungskompatibilität sicherstellen. Damit ist die Fähigkeit gemeint, Objekte unterschiedlicher Versionen eines Typs serialisieren und deserialisieren zu können, ohne die Kernfunktionalität des Typs zu beeinträchtigen. Zum Beispiel kann die erste Version eines Typs nur zwei Felder umfassen. In der nächsten Version des Typs werden mehrere weitere Felder hinzugefügt. Die zweite Version einer Anwendung muss jedoch fähig sein, beide Typen zu serialisieren und zu deserialisieren. In den folgenden Abschnitten wird beschrieben, wie Serialisierung gesteuert wird.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> In Versionen vor .NET Framework 4.0 wurde die Serialisierung benutzerdefinierter Benutzerdaten in einer teilweise vertrauenswürdigen Assembly mithilfe von `GetObjectData` erreicht. Ab Version 4.0 wird diese Methode mit dem <xref:System.Security.SecurityCriticalAttribute>-Attribut markiert, das die Ausführung in teilweise vertrauenswürdigen Assemblys verhindert. Um diese Bedingung zu umgehen, implementieren Sie die <xref:System.Runtime.Serialization.ISafeSerializationData>-Schnittstelle.  
  
## <a name="running-custom-methods-during-and-after-serialization"></a>Ausführen von benutzerdefinierten Methoden während und nach der Serialisierung

Die empfohlene Vorgehensweise zum Ausführen benutzerdefinierter Methoden während und nach der Serialisierung besteht darin, die folgenden Attribute auf Methoden anzuwenden, die zum Korrigieren von Daten während und nach der Serialisierung verwendet werden:  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 Diese Attribute ermöglichen es dem Typ, an jeder einzelnen Phase bzw. an allen vier Phasen des Serialisierungs- und Deserialisierungsprozesses teilzuhaben. Die Attribute geben die Methoden des Typs an, die während jeder Phase aufgerufen werden sollen. Die Methoden greifen nicht auf den Serialisierungsstream zu, sondern ermöglichen es Ihnen, das Objekt vor und nach der Serialisierung bzw. vor oder nach der Deserialisierung zu ändern. Die Attribute können auf allen Vererbungshierarchieebenen des Typs verwendet werden. Jede Methode wird in der Hierarchie von der Basis zur am weitesten abgeleiteten Methode aufgerufen. Durch diesen Mechanismus werden die Komplexität und alle hieraus entstehenden Probleme bei der Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle vermieden, indem die Verantwortung für die Serialisierung und Deserialisierung der am weitesten abgeleiteten Implementierung übergeben wird. Zusätzlich ermöglicht dieser Mechanismus den Formatierungsprogrammen, das Auffüllen von Feldern und das Abrufen von Daten aus dem Serialisierungsstream zu ignorieren. Weitere Informationen und Beispiele zum Steuern der Serialisierung und Deserialisierung erhalten Sie, indem Sie auf einen der oben genannten Links klicken.  
  
 Wenn Sie einem bestehenden serialisierbaren Typ ein neues Feld hinzufügen, wenden Sie außerdem das <xref:System.Runtime.Serialization.OptionalFieldAttribute>-Attribut auf das Feld an. <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignorieren das Fehlen des Felds, wenn ein Stream mit fehlendem neuen Feld verarbeitet wird.  
  
## <a name="implementing-the-iserializable-interface"></a>Implementieren der ISerializable-Schnittstelle  
 Die andere Möglichkeit zum Steuern der Serialisierung besteht in der Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle für ein Objekt. Beachten Sie jedoch, dass die Methode im vorhergehenden Abschnitt beim Steuern der Serialisierung Vorrang vor dieser Methode hat.  
  
 Außerdem dürfen Sie keine Standardserialisierung bei einer Klasse verwenden, die mit dem [Serializable](xref:System.SerializableAttribute)-Attribut markiert ist und für die auf Klassenebene oder für ihre Konstruktoren deklarative oder imperative Sicherheit gilt. Stattdessen sollten diese Klassen immer die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren.  
  
 Die Implementierung von <xref:System.Runtime.Serialization.ISerializable> umfasst auch die Implementierung der `GetObjectData`-Methode und eines speziellen Konstruktors, der bei der Deserialisierung des Objekts verwendet wird. Der folgende Beispielcode zeigt, wie <xref:System.Runtime.Serialization.ISerializable> für die `MyObject`-Klasse aus einem vorherigen Abschnitt implementiert wird.  
  
```csharp
[Serializable]
public class MyObject : ISerializable
{
    public int n1;
    public int n2;
    public String str;

    public MyObject()
    {
    }

    protected MyObject(SerializationInfo info, StreamingContext context)
    {
      n1 = info.GetInt32("i");
      n2 = info.GetInt32("j");
      str = info.GetString("k");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public virtual void GetObjectData(SerializationInfo info, StreamingContext context)
    {
        info.AddValue("i", n1);
        info.AddValue("j", n2);
        info.AddValue("k", str);
    }
}
```

```vb
<Serializable()>  _
Public Class MyObject
    Implements ISerializable
    Public n1 As Integer
    Public n2 As Integer
    Public str As String

    Public Sub New()
    End Sub

    Protected Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        n1 = info.GetInt32("i")
        n2 = info.GetInt32("j")
        str = info.GetString("k")
    End Sub 'New

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overridable Sub GetObjectData(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        info.AddValue("i", n1)
        info.AddValue("j", n2)
        info.AddValue("k", str)
    End Sub
End Class
```  
  
 Wenn **GetObjectData** während der Serialisierung aufgerufen wird, müssen Sie das mit dem Methodenaufruf bereitgestellte <xref:System.Runtime.Serialization.SerializationInfo> auffüllen. Fügen Sie die zu serialisierenden Variablen einfach als Name/Wert-Paar hinzu. Beliebiger Text kann als Name verwendet werden. Sie können frei entscheiden, welche Membervariablen <xref:System.Runtime.Serialization.SerializationInfo> hinzugefügt werden. Voraussetzung ist jedoch, dass genügend Daten serialisiert werden, um das Objekt während der Deserialisierung wiederherzustellen. Abgeleitete Klassen sollten die **GetObjectData** -Methode für das Basisobjekt aufrufen, wenn dieses <xref:System.Runtime.Serialization.ISerializable> implementiert.  
  
 Beachten Sie, dass es durch die Serialisierung anderem Code ermöglicht werden kann, Objektinstanzdaten anzuzeigen oder zu ändern, auf die andernfalls nicht zugegriffen werden . Daher ist für Code, der eine Serialisierung ausführt, [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>-Flags erforderlich. Entsprechend der Standardrichtlinie bedeutet dies, dass diese Berechtigung nicht für aus dem Internet heruntergeladenen Code oder Code aus einem Intranet erteilt wird. Diese Berechtigung wird nur für Code auf dem lokalen Computer erteilt. Die **GetObjectData** -Methode muss entweder durch Anfordern von [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>-Flags oder durch Anfordern von anderen Berechtigungen, die insbesondere private Daten schützen, explizit geschützt werden.  
  
 Wenn in einem privaten Feld vertrauliche Informationen gespeichert werden, sollten Sie die entsprechenden Berechtigungen für **GetObjectData** anfordern, um die Daten zu schützen. Berücksichtigen Sie, dass ein Code, dem die Berechtigung [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des **SerializationFormatter** -Flags erteilt wurde, die in privaten Feldern gespeicherten Daten anzeigen und verändern kann. Ein böswilliger Aufrufer, dem die Berechtigung [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) erteilt wurde, kann Daten, wie etwa ausgeblendete Verzeichnispfade oder erteilte Berechtigungen, anzeigen und die Daten verwenden, um eine Sicherheitslücke auf dem Computer auszunutzen. Eine vollständige Liste der Flags für Sicherheitsberechtigungen, die Sie angeben können, finden Sie unter [SecurityPermissionFlag-Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).  
  
 Beachten Sie, dass in einer Klasse, der <xref:System.Runtime.Serialization.ISerializable> hinzugefügt wurde, sowohl **GetObjectData** als auch der spezielle Konstruktor implementiert werden müssen. Der Compiler gibt eine Warnung aus, wenn **GetObjectData** fehlt. Wenn jedoch der Konstruktor fehlt, wird keine Warnung ausgegeben, da die Implementierung eines Konstruktors nicht erzwungen werden kann. Wenn außerdem versucht wird, eine Klasse ohne den Konstruktor zu deserialisieren, wird eine Ausnahme ausgelöst.  
  
 Der aktuelle Entwurf wurde einer <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A>-Methode vorgezogen, um potenzielle Sicherheits- und Versionsprobleme zu umgehen. Eine `SetObjectData`-Methode muss beispielsweise öffentlich sein, wenn sie als Teil einer Schnittstelle definiert wird. Die Benutzer müssen demnach einen Code schreiben, um zu verhindern, dass die **SetObjectData** -Methode mehrfach aufgerufen wird. Andernfalls kann eine bösartige Anwendung, die die **SetObjectData** -Methode für ein Objekt während der Ausführung eines Vorgangs aufruft, Probleme verursachen.  
  
 Während der Deserialisierung wird <xref:System.Runtime.Serialization.SerializationInfo> an die Klasse übergeben, die den für diesen Zweck bereitgestellten Konstruktor verwendet. Die für den Konstruktor geltenden Sichtbarkeitseinschränkungen werden bei der Deserialisierung des Objekts ignoriert, d.&#160;h., Sie können die Klasse als öffentlich, geschützt, intern oder privat markieren. Der Konstruktor sollte jedoch als geschützt markiert werden, sofern die Klasse nicht versiegelt ist. Ist dies der Fall, sollte der Konstruktor als privat markiert werden Der Konstruktor sollte außerdem eine gründliche Validierung der Eingaben durchführen. Um Missbrauch durch bösartigen Code zu verhindern, muss der Konstruktor dieselben Sicherheitsüberprüfungen und Berechtigungen erzwingen, die zum Abrufen einer Instanz der Klasse durch einen anderen Konstruktor erforderlich sind. Wenn Sie diese Empfehlung nicht umsetzen, kann bösartiger Code ein Objekt im Voraus serialisieren. Der Code kann dann mit der Berechtigung [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>-Flags die Steuerung übernehmen und das Objekt auf einem Clientcomputer deserialisieren, wobei alle Sicherheitseinstellungen umgangen werden, die bei einer standardmäßigen Instanzerstellung mit einem öffentlichen Konstruktor gelten.  
  
 Um den Zustand des Objekts wiederherzustellen, müssen nur die Werte der Variablen aus <xref:System.Runtime.Serialization.SerializationInfo> mithilfe der bei der Serialisierung verwendeten Namen abgerufen werden. Wenn die Basisklasse <xref:System.Runtime.Serialization.ISerializable> implementiert, sollte der Basiskonstruktor aufgerufen werden, damit das Basisobjekt seine Variablen wiederherstellen kann.  
  
 Wenn Sie von einer Klasse, die <xref:System.Runtime.Serialization.ISerializable> implementiert, eine neue Klasse ableiten, muss die abgeleitete Klasse sowohl den Konstruktor als auch die **GetObjectData** -Methode implementieren, wenn sie über zu serialisierende Variablen verfügt. Im folgenden Codebeispiel wird dieser Vorgang unter Verwendung der bereits zuvor gezeigten `MyObject`-Klasse veranschaulicht.  
  
```csharp
[Serializable]
public class ObjectTwo : MyObject
{
    public int num;

    public ObjectTwo()
      : base()
    {
    }

    protected ObjectTwo(SerializationInfo si, StreamingContext context)
      : base(si, context)
    {
        num = si.GetInt32("num");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public override void GetObjectData(SerializationInfo si, StreamingContext context)
    {
        base.GetObjectData(si,context);
        si.AddValue("num", num);
    }
}
```

```vb
<Serializable()>  _
Public Class ObjectTwo
    Inherits MyObject
    Public num As Integer

    Public Sub New()

    End Sub

    Protected Sub New(ByVal si As SerializationInfo, _
    ByVal context As StreamingContext)
        MyBase.New(si, context)
        num = si.GetInt32("num")
    End Sub

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overrides Sub GetObjectData(ByVal si As SerializationInfo, ByVal context As StreamingContext)
        MyBase.GetObjectData(si, context)
        si.AddValue("num", num)
    End Sub
End Class
```  
  
 Vergessen Sie nicht, die Basisklasse im Deserialisierungskonstruktor aufzurufen. Andernfalls wird der Konstruktor für die Basisklasse nicht aufgerufen, und das Objekt wird nach der Deserialisierung nicht vollständig erstellt.  
  
 Objekte werden von innen nach außen rekonstruiert. Dies bedeutet, dass das Aufrufen von Methoden während der Deserialisierung unerwünschte Nebeneffekte haben kann, wenn sich die aufgerufenen Methoden auf Objektverweise beziehen, die zum Zeitpunkt des Aufrufs noch nicht deserialisiert worden sind. Wenn die deserialisierte Klasse <xref:System.Runtime.Serialization.IDeserializationCallback> implementiert, wird die <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A>-Methode automatisch aufgerufen, sobald die gesamte Objektgrafik deserialisiert wurde. Zu diesem Zeitpunkt sind auch die untergeordneten Objekte, auf die verwiesen wurde, vollständig wiederhergestellt. Eine Hashtabelle ist ein typisches Beispiel für eine Klasse, die ohne Verwendung des Ereignislisteners schwer zu deserialisieren ist. Es ist einfach, die Schlüssel- und Wert-Paare während der Deserialisierung abzurufen. Es kann jedoch problematisch sein, diese Objekte dann wieder der Hashtabelle hinzuzufügen, da nicht gewährleistet ist, dass die von der Hashtabelle abgeleiteten Klassen deserialisiert wurden. Daher wird davon abgeraten, zu diesem Zeitpunkt Methoden für Hashtabellen aufzurufen.  
  
## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
- [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)
- [Sicherheit und Serialisierung](../../framework/misc/security-and-serialization.md)
