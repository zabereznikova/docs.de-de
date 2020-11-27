---
title: Objektverweise
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: 55cadc908a3479ee3d104354bcbfd3ea49b15d07
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262371"
---
# <a name="object-references"></a>Objektverweise

In diesem Beispiel wird veranschaulicht, wie Objekte als Verweis zwischen Server und Client übergeben werden. Das Beispiel verwendet simulierte *soziale Netzwerke*. Ein gesellschaftliches Netzwerk besteht aus einer `Person`-Klasse, die eine Liste von Freunden enthält, wobei jeder Freund eine Instanz der `Person`-Klasse mit eigener Liste von Freunden ist. Damit wird ein Objektdiagramm erstellt. Der Dienst macht Operationen in diesen gesellschaftlichen Netzwerken verfügbar.  
  
 In diesem Beispiel wird der Dienst von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="service"></a>Dienst  

 Auf die `Person`-Klasse wurde das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut angewendet, wobei das <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>-Feld zur Deklaration als Verweistyp auf `true` festgelegt wurde. Auf alle Eigenschaften wurde das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut angewendet.  
  
```csharp
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 Der `GetPeopleInNetwork`-Vorgang akzeptiert einen Parameter vom Typ `Person` und gibt alle Personen im Netzwerk; d. h. alle Personen in der `friends`-Liste, die Freunde des Freundes usw. ohne Duplikate zurück.  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 Der `GetMutualFriends`-Vorgang akzeptiert einen Parameter vom Typ `Person` und gibt alle Freunde in der Liste zurück, die diese Person ebenfalls in ihrer `friends`-Liste haben.  
  
```csharp
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 Der `GetCommonFriends`-Vorgang akzeptiert eine Liste vom Typ `Person`. Es wird erwartet, dass die Liste zwei `Person`-Objekte enthält. Der Vorgang gibt eine Liste von `Person`-Objekten zurück, die in den `friends`-Listen beider `Person`-Objekte in der Eingabeliste enthalten sind.  
  
```csharp
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a>Client  

 Der-Client Proxy wird mithilfe des **Dienstverweis hinzufügen** Features von Visual Studio erstellt.  
  
 Ein gesellschaftliches Netzwerk wird erstellt, das aus fünf `Person`-Objekten besteht. Der Client ruft jede der drei Methoden im Dienst auf.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [Interoperable Objektverweise](../feature-details/interoperable-object-references.md)
