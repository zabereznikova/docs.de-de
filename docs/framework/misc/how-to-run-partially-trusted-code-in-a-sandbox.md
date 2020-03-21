---
title: 'Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox'
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: b2f5a72e747f6c71743a7b22fe9f1962ac2f6b53
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181179"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a><span data-ttu-id="eff30-102">Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox</span><span class="sxs-lookup"><span data-stu-id="eff30-102">How to: Run Partially Trusted Code in a Sandbox</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="eff30-103">Unter einer Sandkastenumgebung versteht man das Ausführen von Code in einer beschränkten Sicherheitsumgebung, in der die dem Code gewährten Zugriffsrechte eingeschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="eff30-103">Sandboxing is the practice of running code in a restricted security environment, which limits the access permissions granted to the code.</span></span> <span data-ttu-id="eff30-104">Wenn Sie beispielsweise über eine verwaltete Bibliothek aus einer nicht vollständig vertrauenswürdigen Quelle verfügen, sollten Sie diese nicht als vollständig vertrauenswürdig ausführen.</span><span class="sxs-lookup"><span data-stu-id="eff30-104">For example, if you have a managed library from a source you do not completely trust, you should not run it as fully trusted.</span></span> <span data-ttu-id="eff30-105">Stattdessen sollten Sie den Code in eine Sandkastenumgebung setzen, in der die Berechtigungen des Codes auf diejenigen beschränkt sind, die er voraussichtlich benötigt (z. B. die Berechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).</span><span class="sxs-lookup"><span data-stu-id="eff30-105">Instead, you should place the code in a sandbox that limits its permissions to those that you expect it to need (for example, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission).</span></span>  
  
 <span data-ttu-id="eff30-106">Sie können eine Sandkastenumgebung auch zum Testen von Code verwenden, den Sie verteilen und der in teilweise vertrauenswürdigen Umgebungen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eff30-106">You can also use sandboxing to test code you will be distributing that will run in partially trusted environments.</span></span>  
  
 <span data-ttu-id="eff30-107">Eine <xref:System.AppDomain> ist eine effektive Methode zur Bereitstellung eines Sandkastens für verwaltete Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="eff30-107">An <xref:System.AppDomain> is an effective way of providing a sandbox for managed applications.</span></span> <span data-ttu-id="eff30-108">Anwendungsdomänen, die für die Ausführung von teilweise vertrauenswürdigem Code verwendet werden, weisen Berechtigungen auf, die die geschützten Ressourcen definieren, die bei der Ausführung in dieser <xref:System.AppDomain> verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="eff30-108">Application domains that are used for running partially trusted code have permissions that define the protected resources that are available when running within that <xref:System.AppDomain>.</span></span> <span data-ttu-id="eff30-109">Code, der in der <xref:System.AppDomain> ausgeführt wird, ist von den Berechtigungen gebunden, die mit <xref:System.AppDomain> verbunden sind und darf nur auf die angegebenen Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="eff30-109">Code that runs inside the <xref:System.AppDomain> is bound by the permissions associated with the <xref:System.AppDomain> and is allowed to access only the specified resources.</span></span> <span data-ttu-id="eff30-110">Die <xref:System.AppDomain> enthält zudem auch ein <xref:System.Security.Policy.StrongName>-Array, das verwendet wird, um Assemblys zu identifizieren, die als vollständig vertrauenswürdig geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eff30-110">The <xref:System.AppDomain> also includes a <xref:System.Security.Policy.StrongName> array that is used to identify assemblies that are to be loaded as fully trusted.</span></span> <span data-ttu-id="eff30-111">Damit ist der Ersteller einer <xref:System.AppDomain> in der Lage, eine neue Sandkastendomäne zu starten, die dafür sorgt, dass bestimmte Hilfsassemblys als vollständig vertrauenswürdig gelten.</span><span class="sxs-lookup"><span data-stu-id="eff30-111">This enables the creator of an <xref:System.AppDomain> to start a new sandboxed domain that allows specific helper assemblies to be fully trusted.</span></span> <span data-ttu-id="eff30-112">Eine weitere Option zum Laden von Assemblys als vollständig vertrauenswürdig besteht darin, sie in den globalen Assemblycache zu setzen; damit werden Assemblys jedoch in allen Anwendungsdomänen als vollständig vertrauenswürdig geladen, die auf diesem Computer erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="eff30-112">Another option for loading assemblies as fully trusted is to place them in the global assembly cache; however, that will load assemblies as fully trusted in all application domains created on that computer.</span></span> <span data-ttu-id="eff30-113">Die Liste der starken Namen unterstützt eine auf der jeweiligen <xref:System.AppDomain> basierende Entscheidung, mit der eine restriktivere Festlegung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="eff30-113">The list of strong names supports a per-<xref:System.AppDomain> decision that provides more restrictive determination.</span></span>  
  
 <span data-ttu-id="eff30-114">Sie können die <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Methodenüberladung verwenden, um die Berechtigung anzugeben, die für Anwendungen festgelegt werden, die in einer Sandkastenumgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eff30-114">You can use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> method overload to specify the permission set for applications that run in a sandbox.</span></span> <span data-ttu-id="eff30-115">Mit dieser Überladung sind Sie in der Lage, die exakte Ebene der gewünschten Codezugriffsicherheit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eff30-115">This overload enables you to specify the exact level of code access security you want.</span></span> <span data-ttu-id="eff30-116">Assemblys, die unter Verwendung dieser Überladung in eine <xref:System.AppDomain> geladen werden, können entweder über den angegebenen Berechtigungssatz verfügen oder als vollständig vertrauenswürdig gelten.</span><span class="sxs-lookup"><span data-stu-id="eff30-116">Assemblies that are loaded into an <xref:System.AppDomain> by using this overload can either have the specified grant set only, or can be fully trusted.</span></span> <span data-ttu-id="eff30-117">Der Assembly wird volle Vertrauenswürdigkeit gewährt, wenn sie sich im globalen Assemblycache befindet oder im Arrayparameter `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>) aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="eff30-117">The assembly is granted full trust if it is in the global assembly cache or listed in the `fullTrustAssemblies` (the <xref:System.Security.Policy.StrongName>) array parameter.</span></span> <span data-ttu-id="eff30-118">Nur Assemblys, die bekanntermaßen vollständig vertrauenswürdig sind, sollten der `fullTrustAssemblies`-Liste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="eff30-118">Only assemblies known to be fully trusted should be added to the `fullTrustAssemblies` list.</span></span>  
  
 <span data-ttu-id="eff30-119">Die Überladung hat die folgende Signatur:</span><span class="sxs-lookup"><span data-stu-id="eff30-119">The overload has the following signature:</span></span>  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 <span data-ttu-id="eff30-120">Die Parameter der <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29>-Methodenüberladung geben der Namen der <xref:System.AppDomain> an, den Beweis für die <xref:System.AppDomain>, das <xref:System.AppDomainSetup>-Objekt, das die Anwendungsbasis für den Sandkasten identifiziert, den zu verwendenden Berechtigungssatz und die starken Namen für vollständig vertrauenswürdige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="eff30-120">The parameters for the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload specify the name of the <xref:System.AppDomain>, the evidence for the <xref:System.AppDomain>, the <xref:System.AppDomainSetup> object that identifies the application base for the sandbox, the permission set to use, and the strong names for fully trusted assemblies.</span></span>  
  
 <span data-ttu-id="eff30-121">Aus Sicherheitsgründen sollte die im `info`-Parameter angegebene Anwendungsbasis nicht die Anwendungsbasis der Hostanwendung sein.</span><span class="sxs-lookup"><span data-stu-id="eff30-121">For security reasons, the application base specified in the `info` parameter should not be the application base for the hosting application.</span></span>  
  
 <span data-ttu-id="eff30-122">Im `grantSet`-Parameter können Sie entweder einen Berechtigungssatz angeben, den Sie explizit erstellt haben, oder den standardmäßigen Berechtigungssatz, der von der <xref:System.Security.SecurityManager.GetStandardSandbox%2A>-Methode erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="eff30-122">For the `grantSet` parameter, you can specify either a permission set you have explicitly created, or a standard permission set created by the <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method.</span></span>  
  
 <span data-ttu-id="eff30-123">Im Gegensatz zu den meisten <xref:System.AppDomain>-Ladungen wird der Beweis für die <xref:System.AppDomain> (der vom `securityInfo`-Parameter bereitgestellt wird) nicht zur Festlegung des Berechtigungssatzes für teilweise vertrauenswürdige Assemblys verwendet.</span><span class="sxs-lookup"><span data-stu-id="eff30-123">Unlike most <xref:System.AppDomain> loads, the evidence for the <xref:System.AppDomain> (which is provided by the `securityInfo` parameter) is not used to determine the grant set for the partially trusted assemblies.</span></span> <span data-ttu-id="eff30-124">Dieser wird stattdessen unabhängig vom `grantSet`-Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="eff30-124">Instead, it is independently specified by the `grantSet` parameter.</span></span> <span data-ttu-id="eff30-125">Der Beweis kann jedoch für andere Zwecke wie der Festlegung des isolierten Speicherbereichs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eff30-125">However, the evidence can be used for other purposes such as determining the isolated storage scope.</span></span>  
  
### <a name="to-run-an-application-in-a-sandbox"></a><span data-ttu-id="eff30-126">So führen Sie eine Anwendung in einer Sandkastenumgebung aus</span><span class="sxs-lookup"><span data-stu-id="eff30-126">To run an application in a sandbox</span></span>  
  
1. <span data-ttu-id="eff30-127">Erstellen Sie den Berechtigungssatz, der der nicht vertrauenswürdigen Anwendung gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eff30-127">Create the permission set to be granted to the untrusted application.</span></span> <span data-ttu-id="eff30-128">Die Mindestberechtigung, die Sie gewähren können, ist die Berechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="eff30-128">The minimum permission you can grant is <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span> <span data-ttu-id="eff30-129">Sie können auch weitere Berechtigungen gewähren, von denen Sie annehmen, dass sie für nicht vertrauenswürdigen Code sicher sind, beispielsweise <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span><span class="sxs-lookup"><span data-stu-id="eff30-129">You can also grant additional permissions you think might be safe for untrusted code; for example, <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span></span> <span data-ttu-id="eff30-130">Mit dem folgenden Code wird ein neuer Berechtigungssatz erstellt, der nur die Berechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> enthält.</span><span class="sxs-lookup"><span data-stu-id="eff30-130">The following code creates a new permission set with only <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span>  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     <span data-ttu-id="eff30-131">Alternativ können Sie einen vorhandenen benannte Berechtigungssatz wie "Internet" verwenden.</span><span class="sxs-lookup"><span data-stu-id="eff30-131">Alternatively, you can use an existing named permission set, such as Internet.</span></span>  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     <span data-ttu-id="eff30-132">Die <xref:System.Security.SecurityManager.GetStandardSandbox%2A>-Methode gibt entweder einen `Internet`-Berechtigungssatz oder einen `LocalIntranet`-Berechtigungssatz zurück, abhängig von der im Beweis angegebenen Zone.</span><span class="sxs-lookup"><span data-stu-id="eff30-132">The <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method returns either an `Internet` permission set or a `LocalIntranet` permission set depending on the zone in the evidence.</span></span> <span data-ttu-id="eff30-133"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> konstruiert zudem Identitätsberechtigungen für einige der Beweis-Objekte, die als Verweise übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="eff30-133"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> also constructs identity permissions for some of the evidence objects passed as references.</span></span>  
  
2. <span data-ttu-id="eff30-134">Signieren Sie die Assembly, die die Hostingklasse enthält (in diesem Beispiel `Sandboxer` genannt) und den nicht vertrauenswürdigen Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="eff30-134">Sign the assembly that contains the hosting class (named `Sandboxer` in this example) that calls the untrusted code.</span></span> <span data-ttu-id="eff30-135">Fügen Sie den <xref:System.Security.Policy.StrongName>, der zum Signieren der Assembly verwenden wird, zum <xref:System.Security.Policy.StrongName>-Array des `fullTrustAssemblies`-Parameters des <xref:System.AppDomain.CreateDomain%2A>-Aufrufs hinzu.</span><span class="sxs-lookup"><span data-stu-id="eff30-135">Add the <xref:System.Security.Policy.StrongName> used to sign the assembly to the <xref:System.Security.Policy.StrongName> array of the `fullTrustAssemblies` parameter of the <xref:System.AppDomain.CreateDomain%2A> call.</span></span> <span data-ttu-id="eff30-136">Die Hostingklasse muss als vollständig vertrauenswürdig ausgeführt werden, um die Ausführung von teilweise vertrauenswürdigem Code zu ermöglichen oder um Dienste für die teilweise vertrauenswürdige Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eff30-136">The hosting class must run as fully trusted to enable the execution of the partial-trust code or to offer services to the partial-trust application.</span></span> <span data-ttu-id="eff30-137">Und so lesen Sie den <xref:System.Security.Policy.StrongName> einer Assembly:</span><span class="sxs-lookup"><span data-stu-id="eff30-137">This is how you read the <xref:System.Security.Policy.StrongName> of an assembly:</span></span>  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     <span data-ttu-id="eff30-138">.NET Framework-Assemblys wie mscorlib und System.dll müssen nicht zur Liste der vollständig vertrauenswürdigen Assemblys hinzugefügt werden, da sie als vollständig vertrauenswürdig aus dem globalen Assemblycache geladen werden.</span><span class="sxs-lookup"><span data-stu-id="eff30-138">.NET Framework assemblies such as mscorlib and System.dll do not have to be added to the full-trust list because they are loaded as fully trusted from the global assembly cache.</span></span>  
  
3. <span data-ttu-id="eff30-139">Initialisieren Sie den <xref:System.AppDomainSetup>-Parameter der <xref:System.AppDomain.CreateDomain%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="eff30-139">Initialize the <xref:System.AppDomainSetup> parameter of the <xref:System.AppDomain.CreateDomain%2A> method.</span></span> <span data-ttu-id="eff30-140">Mit diesem Parameter können Sie viele der Einstellungen der neuen <xref:System.AppDomain> steuern.</span><span class="sxs-lookup"><span data-stu-id="eff30-140">With this parameter, you can control many of the settings of the new <xref:System.AppDomain>.</span></span> <span data-ttu-id="eff30-141">Die <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft ist eine wichtige Einstellung und sollte sich von der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft der <xref:System.AppDomain> der Hostanwendung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="eff30-141">The <xref:System.AppDomainSetup.ApplicationBase%2A> property is an important setting, and should be different from the <xref:System.AppDomainSetup.ApplicationBase%2A> property for the <xref:System.AppDomain> of the hosting application.</span></span> <span data-ttu-id="eff30-142">Wenn die <xref:System.AppDomainSetup.ApplicationBase%2A>-Einstellungen die gleichen sind, kann die teilweise vertrauenswürdige Anwendung bewirken, dass die Hostanwendung (als vollständig vertrauenswürdig) eine hiervon definierte Ausnahme lädt, wodurch sie angreifbar wird.</span><span class="sxs-lookup"><span data-stu-id="eff30-142">If the <xref:System.AppDomainSetup.ApplicationBase%2A> settings are the same, the partial-trust application can get the hosting application to load (as fully trusted) an exception it defines, thus exploiting it.</span></span> <span data-ttu-id="eff30-143">Dies ist ein weiterer Grund warum ein Catch (Ausnahme) nicht zu empfehlen ist.</span><span class="sxs-lookup"><span data-stu-id="eff30-143">This is another reason why a catch (exception) is not recommended.</span></span> <span data-ttu-id="eff30-144">Wird die Anwendungsbasis des Hosts anders als die Anwendungsbasis der Anwendung in der Sandboxumgebung eingestellt, verringert sich das Risiko von Angriffen.</span><span class="sxs-lookup"><span data-stu-id="eff30-144">Setting the application base of the host differently from the application base of the sandboxed application mitigates the risk of exploits.</span></span>  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. <span data-ttu-id="eff30-145">Rufen Sie die <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29>-Methodenüberladung auf, um die Anwendungsdomäne mit den angegebenen Parametern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff30-145">Call the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload to create the application domain using the parameters we have specified.</span></span>  
  
     <span data-ttu-id="eff30-146">Die Signatur für diese Methode lautet:</span><span class="sxs-lookup"><span data-stu-id="eff30-146">The signature for this method is:</span></span>  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     <span data-ttu-id="eff30-147">Zusätzliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="eff30-147">Additional information:</span></span>  
  
    - <span data-ttu-id="eff30-148">Dies ist die einzige Überladung der <xref:System.AppDomain.CreateDomain%2A>-Methode, die einen <xref:System.Security.PermissionSet> als Parameter akzeptiert und daher die einzige Überladung, mit der Sie eine Anwendung in einer teilweise vertrauenswürdigen Umgebung laden können.</span><span class="sxs-lookup"><span data-stu-id="eff30-148">This is the only overload of the <xref:System.AppDomain.CreateDomain%2A> method that takes a <xref:System.Security.PermissionSet> as a parameter, and thus the only overload that lets you load an application in a partial-trust setting.</span></span>  
  
    - <span data-ttu-id="eff30-149">Der `evidence`-Parameter wird nicht verwendet, um einen Berechtigungssatz zu berechnen; er wird für die Identifikation durch andere Features von .NET Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="eff30-149">The `evidence` parameter is not used to calculate a permission set; it is used for identification by other features of the .NET Framework.</span></span>  
  
    - <span data-ttu-id="eff30-150">Die Festlegung der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft des `info`-Parameters ist für diese Überladung obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="eff30-150">Setting the <xref:System.AppDomainSetup.ApplicationBase%2A> property of the `info` parameter is mandatory for this overload.</span></span>  
  
    - <span data-ttu-id="eff30-151">Der `fullTrustAssemblies`-Parameter weist das Schlüsselwort `params` auf, was bedeutet, dass es nicht notwendig ist, ein <xref:System.Security.Policy.StrongName>-Array zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff30-151">The `fullTrustAssemblies` parameter has the `params` keyword, which means that it is not necessary to create a <xref:System.Security.Policy.StrongName> array.</span></span> <span data-ttu-id="eff30-152">Die Übergabe von keinem, einem oder mehr starken Namen als Parameter ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="eff30-152">Passing 0, 1, or more strong names as parameters is allowed.</span></span>  
  
    - <span data-ttu-id="eff30-153">Der Code zum Erstellen der Anwendungdomäne ist folgender:</span><span class="sxs-lookup"><span data-stu-id="eff30-153">The code to create the application domain is:</span></span>  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. <span data-ttu-id="eff30-154">Laden Sie den Code in die <xref:System.AppDomain> der von Ihnen erstellten Sandkastenumgebung.</span><span class="sxs-lookup"><span data-stu-id="eff30-154">Load the code into the sandboxing <xref:System.AppDomain> that you created.</span></span> <span data-ttu-id="eff30-155">Dies kann auf zwei Arten erfolgen:</span><span class="sxs-lookup"><span data-stu-id="eff30-155">This can be done in two ways:</span></span>  
  
    - <span data-ttu-id="eff30-156">Rufen Sie die <xref:System.AppDomain.ExecuteAssembly%2A>-Methode für die Assembly auf.</span><span class="sxs-lookup"><span data-stu-id="eff30-156">Call the <xref:System.AppDomain.ExecuteAssembly%2A> method for the assembly.</span></span>  
  
    - <span data-ttu-id="eff30-157">Verwenden Sie die <xref:System.Activator.CreateInstanceFrom%2A>-Methode, um in der neuen <xref:System.AppDomain> eine Instanz einer von <xref:System.MarshalByRefObject> abgeleiteten Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff30-157">Use the <xref:System.Activator.CreateInstanceFrom%2A> method to create an instance of a class derived from <xref:System.MarshalByRefObject> in the new <xref:System.AppDomain>.</span></span>  
  
     <span data-ttu-id="eff30-158">Die zweite Methode ist zu bevorzugen, da es hiermit einfacher ist, Parameter an die neue <xref:System.AppDomain>-Instanz zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="eff30-158">The second method is preferable, because it makes it easier to pass parameters to the new <xref:System.AppDomain> instance.</span></span> <span data-ttu-id="eff30-159">Die <xref:System.Activator.CreateInstanceFrom%2A>-Methode bieten zwei wichtige Funktionen:</span><span class="sxs-lookup"><span data-stu-id="eff30-159">The <xref:System.Activator.CreateInstanceFrom%2A> method provides two important features:</span></span>  
  
    - <span data-ttu-id="eff30-160">Sie können eine Codebasis verwenden, die auf einen Speicherort verweist, der nicht Ihre Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="eff30-160">You can use a code base that points to a location that does not contain your assembly.</span></span>  
  
    - <span data-ttu-id="eff30-161">Sie können die Erstellung unter einem <xref:System.Security.CodeAccessPermission.Assert%2A> für vollständige Vertrauenswürdigkeit (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>) vornehmen, wodurch Sie in der Lage sind, eine Instanz einer kritischen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff30-161">You can do the creation under an <xref:System.Security.CodeAccessPermission.Assert%2A> for full-trust (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), which enables you to create an instance of a critical class.</span></span> <span data-ttu-id="eff30-162">(Dies geschieht immer dann, wenn Ihre Baugruppe keine Transparenzmarkierungen hat und als voll vertrauenswürdig geladen wird.) Daher müssen Sie darauf achten, nur Code zu erstellen, dem Sie mit dieser Funktion vertrauen, und es wird empfohlen, nur Instanzen vollständig vertrauenswürdiger Klassen in der neuen Anwendungsdomäne zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff30-162">(This happens whenever your assembly has no transparency markings and is loaded as fully trusted.) Therefore, you have to be careful to create only code that you trust with this function, and we recommend that you create only instances of fully trusted classes in the new application domain.</span></span>  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     <span data-ttu-id="eff30-163">Beachten Sie, dass die Klasse die <xref:System.MarshalByRefObject>-Klasse erweitern muss, damit eine Instanz einer Klasse in einer neuen Domäne erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="eff30-163">Note that in order to create an instance of a class in a new domain, the class has to extend the <xref:System.MarshalByRefObject> class</span></span>  
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. <span data-ttu-id="eff30-164">Entpacken Sie die neue Domäneninstanz in einen Verweis in dieser Domäne.</span><span class="sxs-lookup"><span data-stu-id="eff30-164">Unwrap the new domain instance into a reference in this domain.</span></span> <span data-ttu-id="eff30-165">Dieser Verweis wird verwendet, um den nicht vertrauenswürdigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eff30-165">This reference is used to execute the untrusted code.</span></span>  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. <span data-ttu-id="eff30-166">Rufen Sie in der `ExecuteUntrustedCode`-Methode der Instanz der soeben erstellten `Sandboxer`-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="eff30-166">Call the `ExecuteUntrustedCode` method in the instance of the `Sandboxer` class you just created.</span></span>  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     <span data-ttu-id="eff30-167">Dieser Aufruf wird in der Anwendungsdomäne in der Sandkastenumgebung ausgeführt, in der es nur eingeschränkte Berechtigungen gibt.</span><span class="sxs-lookup"><span data-stu-id="eff30-167">This call is executed in the sandboxed application domain, which has restricted permissions.</span></span>  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <span data-ttu-id="eff30-168"><xref:System.Reflection> wird verwendet, um ein Handle von einer Methode in der teilweise vertrauenswürdigen Assembly zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eff30-168"><xref:System.Reflection> is used to get a handle of a method in the partially trusted assembly.</span></span> <span data-ttu-id="eff30-169">Das Handle kann verwendet werden, um Code auf sichere Weise mit minimalen Berechtigungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eff30-169">The handle can be used to execute code in a safe way with minimum permissions.</span></span>  
  
     <span data-ttu-id="eff30-170">Beachten Sie im vorherigen Code den <xref:System.Security.PermissionSet.Assert%2A> für die Berechtigung "Volle Vertrauenswürdigkeit", bevor Sie die <xref:System.Security.SecurityException> drucken.</span><span class="sxs-lookup"><span data-stu-id="eff30-170">In the previous code, note the <xref:System.Security.PermissionSet.Assert%2A> for the full-trust permission before printing the <xref:System.Security.SecurityException>.</span></span>  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     <span data-ttu-id="eff30-171">Der Assert "Volle Vertrauenswürdigkeit" wird verwendet, um erweiterte Informationen zu der <xref:System.Security.SecurityException> zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eff30-171">The full-trust assert is used to obtain extended information from the <xref:System.Security.SecurityException>.</span></span> <span data-ttu-id="eff30-172">Ohne den <xref:System.Security.PermissionSet.Assert%2A> erkennt die <xref:System.Security.SecurityException.ToString%2A>-Methode der <xref:System.Security.SecurityException>, dass sich teilweise vertrauenswürdiger Code im Stack befindet und schränkt die zurückgegebenen Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="eff30-172">Without the <xref:System.Security.PermissionSet.Assert%2A>, the <xref:System.Security.SecurityException.ToString%2A> method of <xref:System.Security.SecurityException> will discover that there is partially trusted code on the stack and will restrict the information returned.</span></span> <span data-ttu-id="eff30-173">Dies kann zu Sicherheitsproblemen führen, wenn der teilweise vertrauenswürdige Code auf die Informationen zugreifen kann, das Risiko wird jedoch reduziert, indem keine <xref:System.Security.Permissions.UIPermission> gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="eff30-173">This could cause security issues if the partial-trust code could read that information, but the risk is mitigated by not granting <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="eff30-174">Der Assert "Volle Vertrauenswürdigkeit" sollte sparsam und nur dann verwendet werden, wenn Sie sicher sind, dass Sie teilweise vertrauenswürdigem Code nicht gestatten, auf volle Vertrauenswürdigkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="eff30-174">The full-trust assert should be used sparingly and only when you are sure that you are not allowing partial-trust code to elevate to full trust.</span></span> <span data-ttu-id="eff30-175">Als Regel gilt: Rufen Sie keinen Code, dem Sie nicht vertrauen, in derselben Funktion auf und nachdem einen Assert für volle Vertrauenswürdigkeit aufgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="eff30-175">As a rule, do not call code you do not trust in the same function and after you called an assert for full trust.</span></span> <span data-ttu-id="eff30-176">Es hat sich bewährt, den Assert immer zurückzusetzen, wenn Sie ihn nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="eff30-176">It is good practice to always revert the assert when you have finished using it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eff30-177">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eff30-177">Example</span></span>  
 <span data-ttu-id="eff30-178">Im folgenden Beispiel wird die Prozedur aus dem vorherigen Abschnitt implementiert.</span><span class="sxs-lookup"><span data-stu-id="eff30-178">The following example implements the procedure in the previous section.</span></span> <span data-ttu-id="eff30-179">Im Beispiel enthält ein Projekt mit Namen `Sandboxer` in einer Visual Studio-Lösung auch ein Projekt namens `UntrustedCode`, das die Klasse `UntrustedClass` implementiert.</span><span class="sxs-lookup"><span data-stu-id="eff30-179">In the example, a project named `Sandboxer` in a Visual Studio solution also contains a project named `UntrustedCode`, which implements the class `UntrustedClass`.</span></span> <span data-ttu-id="eff30-180">Bei diesem Szenario wird davon ausgegangen, dass Sie eine Bibliotheksassembly heruntergeladen haben, die eine Methode enthält, von der erwartet wird, dass sie `true` oder `false` zurückgibt, um anzugeben, ob es sich bei der von Ihnen eingegebenen Zahl um eine Fibonacci-Zahl handelt.</span><span class="sxs-lookup"><span data-stu-id="eff30-180">This scenario assumes that you have downloaded a library assembly containing a method that is expected to return `true` or `false` to indicate whether the number you provided is a Fibonacci number.</span></span> <span data-ttu-id="eff30-181">Stattdessen versucht die Methode, eine Datei auf Ihrem Computer zu lesen.</span><span class="sxs-lookup"><span data-stu-id="eff30-181">Instead, the method attempts to read a file from your computer.</span></span> <span data-ttu-id="eff30-182">Das folgende Beispiel zeigt den nicht vertrauenswürdigen Code.</span><span class="sxs-lookup"><span data-stu-id="eff30-182">The following example shows the untrusted code.</span></span>  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="eff30-183">Das folgende Beispiel zeigt den `Sandboxer`-Anwendungscode, der den nicht vertrauenswürdigen Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="eff30-183">The following example shows the `Sandboxer` application code that executes the untrusted code.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="eff30-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eff30-184">See also</span></span>

- [<span data-ttu-id="eff30-185">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="eff30-185">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
