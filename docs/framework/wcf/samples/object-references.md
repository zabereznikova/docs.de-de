---
title: Objektverweise
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: ba4ee3fd0cc16130f66570891ecc295b2d2c50aa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599983"
---
# <a name="object-references"></a><span data-ttu-id="37534-102">Objektverweise</span><span class="sxs-lookup"><span data-stu-id="37534-102">Object References</span></span>
<span data-ttu-id="37534-103">In diesem Beispiel wird veranschaulicht, wie Objekte als Verweis zwischen Server und Client übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="37534-103">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="37534-104">Das Beispiel verwendet simulierte *soziale Netzwerke*.</span><span class="sxs-lookup"><span data-stu-id="37534-104">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="37534-105">Ein gesellschaftliches Netzwerk besteht aus einer `Person`-Klasse, die eine Liste von Freunden enthält, wobei jeder Freund eine Instanz der `Person`-Klasse mit eigener Liste von Freunden ist.</span><span class="sxs-lookup"><span data-stu-id="37534-105">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="37534-106">Damit wird ein Objektdiagramm erstellt.</span><span class="sxs-lookup"><span data-stu-id="37534-106">This creates a graph of objects.</span></span> <span data-ttu-id="37534-107">Der Dienst macht Operationen in diesen gesellschaftlichen Netzwerken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="37534-107">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="37534-108">In diesem Beispiel wird der Dienst von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="37534-108">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37534-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="37534-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="37534-110">Dienst</span><span class="sxs-lookup"><span data-stu-id="37534-110">Service</span></span>  
 <span data-ttu-id="37534-111">Auf die `Person`-Klasse wurde das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut angewendet, wobei das <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>-Feld zur Deklaration als Verweistyp auf `true` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="37534-111">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="37534-112">Auf alle Eigenschaften wurde das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut angewendet.</span><span class="sxs-lookup"><span data-stu-id="37534-112">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
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
  
 <span data-ttu-id="37534-113">Der `GetPeopleInNetwork`-Vorgang akzeptiert einen Parameter vom Typ `Person` und gibt alle Personen im Netzwerk; d. h. alle Personen in der `friends`-Liste, die Freunde des Freundes usw. ohne Duplikate zurück.</span><span class="sxs-lookup"><span data-stu-id="37534-113">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="37534-114">Der `GetMutualFriends`-Vorgang akzeptiert einen Parameter vom Typ `Person` und gibt alle Freunde in der Liste zurück, die diese Person ebenfalls in ihrer `friends`-Liste haben.</span><span class="sxs-lookup"><span data-stu-id="37534-114">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
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
  
 <span data-ttu-id="37534-115">Der `GetCommonFriends`-Vorgang akzeptiert eine Liste vom Typ `Person`.</span><span class="sxs-lookup"><span data-stu-id="37534-115">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="37534-116">Es wird erwartet, dass die Liste zwei `Person`-Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="37534-116">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="37534-117">Der Vorgang gibt eine Liste von `Person`-Objekten zurück, die in den `friends`-Listen beider `Person`-Objekte in der Eingabeliste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="37534-117">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="37534-118">Client</span><span class="sxs-lookup"><span data-stu-id="37534-118">Client</span></span>  
 <span data-ttu-id="37534-119">Der-Client Proxy wird mithilfe des **Dienstverweis hinzufügen** Features von Visual Studio erstellt.</span><span class="sxs-lookup"><span data-stu-id="37534-119">The client proxy is created using the **Add Service Reference** feature of Visual Studio.</span></span>  
  
 <span data-ttu-id="37534-120">Ein gesellschaftliches Netzwerk wird erstellt, das aus fünf `Person`-Objekten besteht.</span><span class="sxs-lookup"><span data-stu-id="37534-120">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="37534-121">Der Client ruft jede der drei Methoden im Dienst auf.</span><span class="sxs-lookup"><span data-stu-id="37534-121">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="37534-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="37534-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="37534-123">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="37534-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="37534-124">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="37534-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="37534-125">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="37534-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="37534-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="37534-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="37534-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="37534-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="37534-128">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37534-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="37534-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="37534-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="37534-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37534-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [<span data-ttu-id="37534-131">Interoperable Objektverweise</span><span class="sxs-lookup"><span data-stu-id="37534-131">Interoperable Object References</span></span>](../feature-details/interoperable-object-references.md)
