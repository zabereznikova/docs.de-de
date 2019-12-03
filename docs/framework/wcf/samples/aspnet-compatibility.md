---
title: ASP.NET-Kompatibilität
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 0938075464a0f2739bdb2a9d8ed1f16f61edff2b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716160"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="296ff-102">ASP.NET-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="296ff-102">ASP.NET Compatibility</span></span>

<span data-ttu-id="296ff-103">In diesem Beispiel wird veranschaulicht, wie der ASP.NET-Kompatibilitätsmodus in Windows Communication Foundation (WCF) aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="296ff-103">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="296ff-104">Dienste, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden, sind vollständig in der ASP.NET-Anwendungs Pipeline und können ASP.NET-Funktionen wie die Datei-/URL-Autorisierung, den Sitzungs Status und die <xref:System.Web.HttpContext>-Klasse nutzen.</span><span class="sxs-lookup"><span data-stu-id="296ff-104">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="296ff-105">Die <xref:System.Web.HttpContext>-Klasse ermöglicht den Zugriff auf Cookies, Sitzungen und andere ASP.NET-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="296ff-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="296ff-106">Dieser Modus erfordert, dass die Bindungen den HTTP-Transport verwenden und der Dienst selbst in IIS gehostet ist.</span><span class="sxs-lookup"><span data-stu-id="296ff-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>

<span data-ttu-id="296ff-107">In diesem Beispiel ist der Client eine Konsolenanwendung (eine ausführbare Datei), und der Dienst wird in Internetinformationsdiensten (IIS) gehostet.</span><span class="sxs-lookup"><span data-stu-id="296ff-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="296ff-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="296ff-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="296ff-109">Für dieses Beispiel ist ein .NET Framework 4-Anwendungs Pool erforderlich, um ausgeführt werden zu können.</span><span class="sxs-lookup"><span data-stu-id="296ff-109">This sample requires a .NET Framework 4 application pool in order to run.</span></span> <span data-ttu-id="296ff-110">Führen Sie die folgenden Schritte aus, um einen neuen Anwendungspool zu erstellen oder den Standardanwendungspool zu ändern.</span><span class="sxs-lookup"><span data-stu-id="296ff-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>

1. <span data-ttu-id="296ff-111">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="296ff-111">Open **Control Panel**.</span></span>  <span data-ttu-id="296ff-112">Öffnen Sie das Applet " **Verwaltung** " unter der Überschrift " **System und Sicherheit** ".</span><span class="sxs-lookup"><span data-stu-id="296ff-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="296ff-113">Öffnen Sie das Applet **Internetinformationsdienste (IIS)-Manager** .</span><span class="sxs-lookup"><span data-stu-id="296ff-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>

2. <span data-ttu-id="296ff-114">Erweitern Sie im Bereich **Verbindungen** den Eintrag TreeView.</span><span class="sxs-lookup"><span data-stu-id="296ff-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="296ff-115">Wählen Sie den Knoten **Anwendungs Pools** aus.</span><span class="sxs-lookup"><span data-stu-id="296ff-115">Select the **Application Pools** node.</span></span>

3. <span data-ttu-id="296ff-116">Klicken Sie mit der rechten Maustaste auf das Listenelement **DefaultAppPool** , und wählen Sie **Grundeinstellungen...** aus, um den Standard Anwendungs Pool für die Verwendung von .NET Framework 4 festzulegen (was zu Inkompatibilitäts Problemen bei vorhandenen Websites führen kann).</span><span class="sxs-lookup"><span data-stu-id="296ff-116">To set the default application pool to use .NET Framework 4 (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="296ff-117">Legen Sie den pulldowndown der **.NET Framework-Version** auf **.NET Framework v 4.0.30128** (oder höher) fest.</span><span class="sxs-lookup"><span data-stu-id="296ff-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>

4. <span data-ttu-id="296ff-118">Um einen neuen Anwendungs Pool zu erstellen, der .NET Framework 4 verwendet (um die Kompatibilität für andere Anwendungen beizubehalten), klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungs Pools** , und wählen Sie **Anwendungs Pool hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="296ff-118">To create a new application pool that uses .NET Framework 4 (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="296ff-119">Benennen Sie den neuen Anwendungs Pool, und legen Sie den pulldowndownvorgang der **.NET Framework-Version** auf **.NET Framework v 4.0.30128** (oder höher) fest.</span><span class="sxs-lookup"><span data-stu-id="296ff-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="296ff-120">Nachdem Sie die Schritte unten ausgeführt haben, klicken Sie mit der rechten Maustaste auf die Anwendung **Service Model Samples** , und wählen Sie **Anwendung verwalten**, **Erweiterte Einstellungen...** aus.</span><span class="sxs-lookup"><span data-stu-id="296ff-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="296ff-121">Legen Sie den **Anwendungs Pool** auf den neuen Anwendungs Pool fest.</span><span class="sxs-lookup"><span data-stu-id="296ff-121">Set the **Application Pool** to the new application pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="296ff-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="296ff-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="296ff-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="296ff-123">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="296ff-124">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="296ff-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="296ff-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="296ff-125">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

<span data-ttu-id="296ff-126">Dieses Beispiel basiert auf den ersten Schritten, durch die ein Rechner Dienst [implementiert wird.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="296ff-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="296ff-127">Der `ICalculator`-Vertrag wurde als `ICalculatorSession`-Vertrag geändert, damit eine Reihe von Vorgängen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="296ff-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculatorSession
{
    [OperationContract]
    void Clear();
    [OperationContract]
    void AddTo(double n);
    [OperationContract]
    void SubtractFrom(double n);
    [OperationContract]
    void MultiplyBy(double n);
    [OperationContract]
    void DivideBy(double n);
    [OperationContract]
    double Result();
}
```

<span data-ttu-id="296ff-128">Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst mithilfe der Funktion den Status für jeden Client bei.</span><span class="sxs-lookup"><span data-stu-id="296ff-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="296ff-129">Der Client kann das aktuelle Ergebnis abrufen, indem er `Result` aufruft, und es auf null löschen, indem er `Clear` aufruft.</span><span class="sxs-lookup"><span data-stu-id="296ff-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>

<span data-ttu-id="296ff-130">Der Dienst verwendet die ASP.NET-Sitzung, um das Ergebnis für jede Client Sitzung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="296ff-130">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="296ff-131">Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jeden Client über mehrere Aufrufe des Diensts hinweg beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="296ff-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>

> [!NOTE]
> <span data-ttu-id="296ff-132">ASP.NET-Sitzungs Status und WCF-Sitzungen sind sehr unterschiedliche Dinge.</span><span class="sxs-lookup"><span data-stu-id="296ff-132">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="296ff-133">Weitere Informationen zu WCF-Sitzungen finden Sie in der [Sitzung](../../../../docs/framework/wcf/samples/session.md) .</span><span class="sxs-lookup"><span data-stu-id="296ff-133">See [Session](../../../../docs/framework/wcf/samples/session.md) for details on WCF sessions.</span></span>

<span data-ttu-id="296ff-134">Der Dienst hat eine intime Abhängigkeit vom ASP.NET-Sitzungszustand und erfordert den ASP.NET-Kompatibilitätsmodus, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="296ff-134">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="296ff-135">Diese Anforderungen werden deklarativ durch die Übernahme des `AspNetCompatibilityRequirements`-Attributs ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="296ff-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>

```csharp
[AspNetCompatibilityRequirements(RequirementsMode =
                       AspNetCompatibilityRequirementsMode.Required)]
public class CalculatorService : ICalculatorSession
{
    double Result
    {  // store result in AspNet Session
       get {
          if (HttpContext.Current.Session["Result"] != null)
             return (double)HttpContext.Current.Session["Result"];
          return 0.0D;
       }
       set
       {
          HttpContext.Current.Session["Result"] = value;
       }
    }
    public void Clear()
    {
        Result = 0.0D;
    }
    public void AddTo(double n)
    {
        Result += n;
    }
    public void SubtractFrom(double n)
    {
        Result -= n;
    }
    public void MultiplyBy(double n)
    {
        Result *= n;
    }
    public void DivideBy(double n)
    {
        Result /= n;
    }
    public double Result()
    {
        return Result;
    }
}
```

<span data-ttu-id="296ff-136">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="296ff-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="296ff-137">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="296ff-137">Press ENTER in the client window to shut down the client.</span></span>

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="296ff-138">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="296ff-138">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="296ff-139">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="296ff-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="296ff-140">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="296ff-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="296ff-141">Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup. bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten.</span><span class="sxs-lookup"><span data-stu-id="296ff-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="296ff-142">Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="296ff-142">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="296ff-143">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="296ff-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="296ff-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="296ff-144">See also</span></span>

- [<span data-ttu-id="296ff-145">AppFabric-Hosting-und persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="296ff-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
