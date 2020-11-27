---
title: Durchführen eines Identitätswechsels für den Client
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: bc4ff2d4b53b679266978ae5ffdea97e4606a351
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281897"
---
# <a name="impersonating-the-client"></a><span data-ttu-id="fa3f0-102">Durchführen eines Identitätswechsels für den Client</span><span class="sxs-lookup"><span data-stu-id="fa3f0-102">Impersonating the Client</span></span>

<span data-ttu-id="fa3f0-103">Das Beispiel für einen Identitätswechsel veranschaulicht, wie die Identität der Aufruferanwendung vom Dienst angenommen wird, sodass der Dienst im Namen des Aufrufers auf Systemressourcen zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-103">The Impersonation sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>  
  
 <span data-ttu-id="fa3f0-104">Dieses Beispiel basiert auf dem [Self-Host-](self-host.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-104">This sample is based on the [Self-Host](self-host.md) sample.</span></span> <span data-ttu-id="fa3f0-105">Die Dienst-und Client Konfigurationsdateien sind identisch mit denen des [Self-Host-](self-host.md) Beispiels.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-105">The service and client configuration files are the same as that of the [Self-Host](self-host.md) sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa3f0-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fa3f0-107">Im folgenden Codebeispiel wird gezeigt, dass der Servicecode so geändert wurde, dass die `Add`-Methode für den Dienst die Identität des Aufrufers mithilfe von <xref:System.ServiceModel.OperationBehaviorAttribute> annimmt.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-107">The service code has been modified such that the `Add` method on the service impersonates the caller using the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="fa3f0-108">Demzufolge wird der Sicherheitskontext des ausgeführten Threads so geändert, dass die Identität des Aufrufers angenommen wird, bevor die `Add`-Methode eingegeben und auf das Beenden der Methode zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-108">As a result, the security context of the executing thread is switched to impersonate the caller before entering the `Add` method and reverted on exiting the method.</span></span>  
  
 <span data-ttu-id="fa3f0-109">Die im folgenden Codebeispiel veranschaulichte `DisplayIdentityInformation`-Methode ist eine Hilfsfunktion, mit der die Identität des Aufrufers dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-109">The `DisplayIdentityInformation` method shown in the following sample code is a utility function that displays the caller's identity.</span></span>  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 <span data-ttu-id="fa3f0-110">Im folgenden Codebeispiel wird gezeigt, dass die `Subtract`-Methode für den Dienst die Identität des Aufrufers mithilfe von imperativen Aufrufen annimmt.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-110">The `Subtract` method on the service impersonates the caller using imperative calls as shown in the following sample code.</span></span>  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs
            // on the system resource are enforced in the caller's context.
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="fa3f0-111">Beachten Sie, dass in diesem Fall kein Identitätswechsel für den gesamten Aufruf, sondern nur für einen Teil des Aufrufs vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-111">Note that in this case the caller is not impersonated for the entire call but is only impersonated for a portion of the call.</span></span> <span data-ttu-id="fa3f0-112">Im Allgemeinen empfiehlt es sich, einen Identitätswechsel für den kleinsten Bereich und nicht für den ganzen Vorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-112">In general, impersonating for the smallest scope is preferable to impersonating for the entire operation.</span></span>  
  
 <span data-ttu-id="fa3f0-113">Die anderen Methoden nehmen die Identität des Aufrufers nicht an.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-113">The other methods do not impersonate the caller.</span></span>  
  
 <span data-ttu-id="fa3f0-114">Der Clientcode wurde geändert, um die Identitätswechselebene auf <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-114">The client code has been modified to set the impersonation level to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span></span> <span data-ttu-id="fa3f0-115">Der Client gibt die vom Dienst zu verwendende Identitätswechselebene durch die <xref:System.Security.Principal.TokenImpersonationLevel>-Enumeration an.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-115">The client specifies the impersonation level to be used by the service, by using the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration.</span></span> <span data-ttu-id="fa3f0-116">Die Enumeration unterstützt die folgenden Werte: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> und <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-116">The enumeration supports the following values: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> and <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span> <span data-ttu-id="fa3f0-117">Um beim Zugreifen auf die Systemressource auf dem lokalen Rechner, der mit Windows-Zugriffssteuerungslisten geschützt ist, eine Zugriffsprüfung durchzuführen, muss die Identitätswechselebene auf <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> festgelegt sein, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-117">To perform an access check when accessing a system resource on the local machine that is protected using Windows ACLs, the impersonation level must be set to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, as shown in the following sample code.</span></span>  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 <span data-ttu-id="fa3f0-118">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-118">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="fa3f0-119">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-119">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa3f0-120">Der Dienst muss entweder unter einem Administrator Konto ausgeführt werden, oder das Konto, unter dem er ausgeführt wird, muss über Rechte zum Registrieren des `http://localhost:8000/ServiceModelSamples` URIs bei der HTTP-Ebene verfügen.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-120">The service must either run under an administrative account or the account it runs under must be granted rights to register the `http://localhost:8000/ServiceModelSamples` URI with the HTTP layer.</span></span> <span data-ttu-id="fa3f0-121">Solche Rechte können durch das Einrichten einer [Namespace Reservierung](/windows/win32/http/namespace-reservations-registrations-and-routing) mithilfe des [Httpcfg.exe Tools](/windows/win32/http/httpcfg-exe)erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-121">Such rights can be granted by setting up a [Namespace Reservation](/windows/win32/http/namespace-reservations-registrations-and-routing) using the [Httpcfg.exe tool](/windows/win32/http/httpcfg-exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa3f0-122">Auf Computern, auf denen Windows Server 2003 ausgeführt wird, wird der Identitätswechsel nur unterstützt, wenn die Host.exe Anwendung über das Identitätswechsel Privileg verfügt.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-122">On computers running Windows Server 2003, impersonation is supported only if the Host.exe application has the Impersonation privilege.</span></span> <span data-ttu-id="fa3f0-123">(Standardmäßig verfügen nur Administratoren über diese Berechtigung.) Um dieses Privileg einem Konto hinzuzufügen, unter dem der-Dienst ausgeführt wird, wechseln Sie zu **Verwaltung**, öffnen Sie **lokale Sicherheitsrichtlinie**, öffnen Sie **lokale Richtlinien**, klicken Sie auf Zuweisen von **Benutzerrechten**, und wählen Sie dann Identität **eines Clients nach Authentifizierung** annehmen aus, und doppelklicken Sie auf **Eigenschaften** , um einen Benutzer oder eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="fa3f0-123">(By default, only administrators have this permission.) To add this privilege to an account the service is running as, go to **Administrative Tools**, open **Local Security Policy**, open **Local Policies**, click **User Rights Assignment**, and select **Impersonate a Client after Authentication** and double-click **Properties** to add a user or group.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fa3f0-124">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fa3f0-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="fa3f0-125">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="fa3f0-126">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="fa3f0-127">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa3f0-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="fa3f0-128">Wenn Sie veranschaulichen möchten, dass der Dienst die Identität des Aufrufers annimmt, führen Sie den Client auf einem anderen Konto als dem Konto aus, auf dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-128">To demonstrate that the service impersonates the caller, run the client under a different account than the one the service is running under.</span></span> <span data-ttu-id="fa3f0-129">Geben Sie dazu an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fa3f0-129">To do so, at the command prompt, type:</span></span>  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     <span data-ttu-id="fa3f0-130">Sie werden anschließend zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-130">You are then prompted for a password.</span></span> <span data-ttu-id="fa3f0-131">Geben Sie das Kennwort für das Konto ein, das Sie vorher angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-131">Enter the password for the account you previously specified.</span></span>  
  
5. <span data-ttu-id="fa3f0-132">Wenn Sie den Client ausführen, beachten Sie die Identität vor und nach dem Ausführen mit unterschiedlichen Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="fa3f0-132">When you run the client, note the identity before and after running it with different credentials.</span></span>  
