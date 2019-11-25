---
title: 'Entschärfung: Deserialisierung von Objekten über App-Domänen'
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: e2d90a77cab699646bd31eaa162d1bd1744fd51b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457928"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a><span data-ttu-id="a632c-102">Entschärfung: Deserialisierung von Objekten über App-Domänen</span><span class="sxs-lookup"><span data-stu-id="a632c-102">Mitigation: Deserialization of Objects Across App Domains</span></span>
<span data-ttu-id="a632c-103">In Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a632c-103">In some cases, when an app uses two or more app domains with different application bases, the attempt to deserialize objects in the logical call context across app domains throws an exception.</span></span>  
  
## <a name="diagnosing-the-issue"></a><span data-ttu-id="a632c-104">Diagnose des Problems</span><span class="sxs-lookup"><span data-stu-id="a632c-104">Diagnosing the issue</span></span>  
 <span data-ttu-id="a632c-105">Das Problem tritt bei der folgenden Abfolge von Bedingungen auf:</span><span class="sxs-lookup"><span data-stu-id="a632c-105">The issue arises under the following sequence of conditions:</span></span>  
  
1. <span data-ttu-id="a632c-106">Eine Anwendung verwendet zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen.</span><span class="sxs-lookup"><span data-stu-id="a632c-106">An app uses two or more app domains with different application bases.</span></span>  
  
2. <span data-ttu-id="a632c-107">Einige Typen werden explizit zu <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> hinzugefügt, indem eine Methode wie <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> oder <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a632c-107">Some types are explicitly added to the <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> by calling a method such as <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> or <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a632c-108">Diese Typen werden nicht als serialisierbar markiert und werden nicht im globalen Assemblycache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a632c-108">These types are not marked as serializable and are not stored in the global assembly cache.</span></span>  
  
3. <span data-ttu-id="a632c-109">Später versucht Code, der in der nicht standardmäßigen App-Domäne ausgeführt wird, einen Wert aus einer Konfigurationsdatei zu lesen oder XML für die Deserialisierung eines Objekts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a632c-109">Later, code running in the non-default app domain tries to read a value from a configuration file or use XML to deserialize an object.</span></span>  
  
4. <span data-ttu-id="a632c-110">Um aus einer Konfigurationsdatei zu lesen oder das Objekt zu deserialisieren, versucht ein <xref:System.Xml.XmlReader>-Objekt auf das Konfigurationssystem zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a632c-110">In order to read from a configuration file or deserialize the object, an <xref:System.Xml.XmlReader> object tries to access the configuration system.</span></span>  
  
5. <span data-ttu-id="a632c-111">Wenn das Konfigurationssystem noch nicht initialisiert wurde, muss es seine Initialisierung abschließen.</span><span class="sxs-lookup"><span data-stu-id="a632c-111">If the configuration system has not already been initialized, it must complete its initialization.</span></span> <span data-ttu-id="a632c-112">Dies bedeutet unter anderem, dass die Laufzeit wie folgt einen stabilen Pfad für ein Konfigurationssystem erstellen muss:</span><span class="sxs-lookup"><span data-stu-id="a632c-112">This means, among other things, that the runtime has to create a stable path for a configuration system, which it does as follows:</span></span>  
  
    1. <span data-ttu-id="a632c-113">Sie sucht nach einem Beweis für die nicht standardmäßige App-Domäne.</span><span class="sxs-lookup"><span data-stu-id="a632c-113">It looks for evidence for the non-default app domain.</span></span>  
  
    2. <span data-ttu-id="a632c-114">Sie versucht, den Beweis für die nicht standardmäßige App-Domäne auf Grundlage der Standard-App-Domäne zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="a632c-114">It tries to calculate the evidence for the non-default app domain based on the default app domain.</span></span>  
  
    3. <span data-ttu-id="a632c-115">Der Aufruf, um einen Beweis für die Standard-App-Domäne zu erhalten, löst einen Aufruf über die App-Domänen hinweg auf, der von der nicht standardmäßigen App-Domäne zur Standard-App-Domäne verläuft.</span><span class="sxs-lookup"><span data-stu-id="a632c-115">The call to get evidence for the default app domain triggers a cross-app domain call from the non-default app domain to the default app domain.</span></span>  
  
    4. <span data-ttu-id="a632c-116">Im Rahmen des über die App-Domänengrenzen hinweg geltenden Vertrags in .NET Framework muss der Inhalt des logischen Aufrufkontexts auch über App-Domänengrenzen hinweg gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="a632c-116">As part of the cross-app domain contract in the .NET Framework, the contents of the logical call context also have to be marshaled across app domain boundaries.</span></span>  
  
6. <span data-ttu-id="a632c-117">Da die Typen im logischen Aufrufkontext nicht in der Standard-App-Domäne aufgelöst werden können, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a632c-117">Because the types that are in the logical call context cannot be resolved in the default app domain, an exception is thrown.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a632c-118">Minderung</span><span class="sxs-lookup"><span data-stu-id="a632c-118">Mitigation</span></span>  
 <span data-ttu-id="a632c-119">Gehen Sie wie folgt vor, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="a632c-119">To work around this issue, do the following</span></span>  
  
1. <span data-ttu-id="a632c-120">Suchen Sie bei Auftreten der Ausnahme nach dem Aufruf von `get_Evidence` in der Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="a632c-120">Look for the call to `get_Evidence` in the call stack when the exception is thrown.</span></span> <span data-ttu-id="a632c-121">Bei der Ausnahme kann es sich um verschiedene Ausnahmen handeln, einschließlich <xref:System.IO.FileNotFoundException> und <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="a632c-121">The exception can be any of a large subset of exceptions, including <xref:System.IO.FileNotFoundException> and <xref:System.Runtime.Serialization.SerializationException>.</span></span>  
  
2. <span data-ttu-id="a632c-122">Identifizieren Sie die Position in der App, an der keine Objekte zum logischen Aufrufkontext hinzugefügt werden, und fügen Sie folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="a632c-122">Identify the place in the app where no objects are added to the logical call context and add the following code:</span></span>  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a><span data-ttu-id="a632c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a632c-123">See also</span></span>

- [<span data-ttu-id="a632c-124">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="a632c-124">Application compatibility</span></span>](application-compatibility.md)
