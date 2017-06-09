---
title: "Objektverweise | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Objektverweise
In diesem Beispiel wird veranschaulicht, wie Objekte als Verweis zwischen Server und Client übergeben werden.Im Beispiel werden simulierte *gesellschaftliche Netzwerke* verwendet.Ein gesellschaftliches Netzwerk besteht aus einer `Person`\-Klasse, die eine Liste von Freunden enthält, wobei jeder Freund eine Instanz der `Person`\-Klasse mit eigener Liste von Freunden ist.Damit wird ein Objektdiagramm erstellt.Der Dienst macht Operationen in diesen gesellschaftlichen Netzwerken verfügbar.  
  
 In diesem Beispiel wird der Dienst von Internetinformationsdiensten \(IIS\) gehostet, und der Client ist eine Konsolenanwendung \(.exe\).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## Dienst  
 Auf die `Person`\-Klasse wurde das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut angewendet, wobei das <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>\-Feld zur Deklaration als Verweistyp auf `true` festgelegt wurde.Auf alle Eigenschaften wurde das <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut angewendet.  
  
```  
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
  
 Der `GetPeopleInNetwork`\-Vorgang akzeptiert einen Parameter vom Typ `Person` und gibt alle Personen im Netzwerk; d. h. alle Personen in der `friends`\-Liste, die Freunde des Freundes usw. ohne Duplikate zurück.  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 Der `GetMutualFriends`\-Vorgang akzeptiert einen Parameter vom Typ `Person` und gibt alle Freunde in der Liste zurück, die diese Person ebenfalls in ihrer `friends`\-Liste haben.  
  
```  
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
  
 Der `GetCommonFriends`\-Vorgang akzeptiert eine Liste vom Typ `Person`.Es wird erwartet, dass die Liste zwei `Person`\-Objekte enthält.Der Vorgang gibt eine Liste von `Person`\-Objekten zurück, die in den `friends`\-Listen beider `Person`\-Objekte in der Eingabeliste enthalten sind.  
  
```  
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## Client  
 Der Clientproxy wird mit der Funktion **Dienstverweis hinzufügen** von [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] erstellt.  
  
 Ein gesellschaftliches Netzwerk wird erstellt, das aus fünf `Person`\-Objekten besteht.Der Client ruft jede der drei Methoden im Dienst auf.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>   
 [Interoperable Objektverweise](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)