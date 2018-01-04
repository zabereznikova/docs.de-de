---
title: "ASP.NET-Kompatibilität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 751fe96caa2be63e925b3107fa2c198b523bef72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="64568-102">ASP.NET-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="64568-102">ASP.NET Compatibility</span></span>
<span data-ttu-id="64568-103">In diesem Beispiel wird veranschaulicht, wie der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Kompatibilitätsmodus in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="64568-103">This sample demonstrates how to enable [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="64568-104">Dienste, die im [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Kompatibilitätsmodus ausgeführt werden, nehmen vollständig an der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendungspipeline teil und können [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Funktionen, wie Datei-/URL-Autorisierung, Sitzungsstatus und die <xref:System.Web.HttpContext>-Klasse, nutzen.</span><span class="sxs-lookup"><span data-stu-id="64568-104">Services running in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode participate fully in the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application pipeline and can make use of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="64568-105">Die <xref:System.Web.HttpContext>-Klasse lässt Zugriff auf Cookies, Sitzungen und andere [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Funktionen zu.</span><span class="sxs-lookup"><span data-stu-id="64568-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features.</span></span> <span data-ttu-id="64568-106">Dieser Modus erfordert, dass die Bindungen den HTTP-Transport verwenden und der Dienst selbst in IIS gehostet ist.</span><span class="sxs-lookup"><span data-stu-id="64568-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>  
  
 <span data-ttu-id="64568-107">In diesem Beispiel ist der Client eine Konsolenanwendung (eine ausführbare Datei), und der Dienst wird in Internetinformationsdiensten (IIS) gehostet.</span><span class="sxs-lookup"><span data-stu-id="64568-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64568-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="64568-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64568-109">Damit das Beispiel ausgeführt werden kann, muss ein [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]-Anwendungspool verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="64568-109">This sample requires a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] application pool in order to run.</span></span> <span data-ttu-id="64568-110">Führen Sie die folgenden Schritte aus, um einen neuen Anwendungspool zu erstellen oder den Standardanwendungspool zu ändern.</span><span class="sxs-lookup"><span data-stu-id="64568-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>  
>   
>  1.  <span data-ttu-id="64568-111">Open **in der Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="64568-111">Open **Control Panel**.</span></span>  <span data-ttu-id="64568-112">Öffnen der **Verwaltung** Applet unter der **System und Sicherheit** Überschrift.</span><span class="sxs-lookup"><span data-stu-id="64568-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="64568-113">Öffnen der **(Internet Information Services, IIS) Manager** Applet ".</span><span class="sxs-lookup"><span data-stu-id="64568-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>  
> 2.  <span data-ttu-id="64568-114">Erweitern Sie die Strukturansicht, in der **Verbindungen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="64568-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="64568-115">Wählen Sie die **Anwendungspools** Knoten.</span><span class="sxs-lookup"><span data-stu-id="64568-115">Select the **Application Pools** node.</span></span>  
> 3.  <span data-ttu-id="64568-116">Festlegen der Standardanwendungspool verwendet [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (Dies verursacht möglicherweise Inkompatibilitätsprobleme mit vorhandenen Websites), mit der rechten Maustaste die **DefaultAppPool** Element aus, und wählen Sie **Grundeinstellungen...** .</span><span class="sxs-lookup"><span data-stu-id="64568-116">To set the default application pool to use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="64568-117">Legen Sie die **.Net Framework-Version** Pulldownliste **.Net Framework v4.0.30128** (oder höher).</span><span class="sxs-lookup"><span data-stu-id="64568-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>  
> 4.  <span data-ttu-id="64568-118">Um einen neuen Anwendungspool erstellen, verwendet [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (um die Kompatibilität mit anderen Anwendungen beizubehalten), mit der rechten Maustaste die **Anwendungspools** Knoten, und wählen **Anwendungspool hinzufügen...** .</span><span class="sxs-lookup"><span data-stu-id="64568-118">To create a new application pool that uses [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="64568-119">Benennen Sie den neuen Anwendungspool, und legen die **.Net Framework-Version** Pulldownliste **.Net Framework v4.0.30128** (oder höher).</span><span class="sxs-lookup"><span data-stu-id="64568-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="64568-120">Nach dem Ausführen des Setups unten aufgeführten Schritte, mit der rechten Maustaste die **ServiceModelSamples** Anwendung, und wählen **-Anwendung verwalten**, **Erweiterte Einstellungen...** .</span><span class="sxs-lookup"><span data-stu-id="64568-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="64568-121">Legen Sie die **Anwendungspool** auf den neuen Anwendungspool.</span><span class="sxs-lookup"><span data-stu-id="64568-121">Set the **Application Pool** to the new application pool.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64568-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="64568-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="64568-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="64568-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="64568-124">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="64568-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64568-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="64568-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 <span data-ttu-id="64568-126">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert einen rechnerdienst.</span><span class="sxs-lookup"><span data-stu-id="64568-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="64568-127">Der `ICalculator`-Vertrag wurde als `ICalculatorSession`-Vertrag geändert, damit eine Reihe von Vorgängen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="64568-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>  
  
```  
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
  
 <span data-ttu-id="64568-128">Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst mithilfe der Funktion den Status für jeden Client bei.</span><span class="sxs-lookup"><span data-stu-id="64568-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="64568-129">Der Client kann das aktuelle Ergebnis abrufen, indem er `Result` aufruft, und es auf null löschen, indem er `Clear` aufruft.</span><span class="sxs-lookup"><span data-stu-id="64568-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>  
  
 <span data-ttu-id="64568-130">Der Dienst verwendet die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Sitzung, um die Ergebnisse für jede Clientsitzung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="64568-130">The service uses the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session to store the result for each client session.</span></span> <span data-ttu-id="64568-131">Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jeden Client über mehrere Aufrufe des Diensts hinweg beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="64568-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="64568-132">-Sitzungsstatus und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sitzungen sind unterschiedliche Dinge.</span><span class="sxs-lookup"><span data-stu-id="64568-132"> session state and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions are very different things.</span></span>  <span data-ttu-id="64568-133">Finden Sie unter der [Sitzung](../../../../docs/framework/wcf/samples/session.md) ausführliche [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="64568-133">See the [Session](../../../../docs/framework/wcf/samples/session.md) for details on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions.</span></span>  
  
 <span data-ttu-id="64568-134">Der Dienst verfügt über eine enge Abhängigkeit vom [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Sitzungsstatus und erfordert den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Kompatibilitätsmodus, um korrekt zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="64568-134">The service has an intimate dependency on [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session state and requires [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compatibility mode to function correctly.</span></span> <span data-ttu-id="64568-135">Diese Anforderungen werden deklarativ durch die Übernahme des `AspNetCompatibilityRequirements`-Attributs ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="64568-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>  
  
```  
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
  
 <span data-ttu-id="64568-136">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64568-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="64568-137">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="64568-137">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="64568-138">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="64568-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="64568-139">Achten Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64568-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="64568-140">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="64568-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="64568-141">Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples-Anwendung in [!INCLUDE[iisver](../../../../includes/iisver-md.md)] einzurichten.</span><span class="sxs-lookup"><span data-stu-id="64568-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="64568-142">Das Verzeichnis ServiceModelSamples sollte jetzt als [!INCLUDE[iisver](../../../../includes/iisver-md.md)]-Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="64568-142">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="64568-143">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64568-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64568-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64568-144">See Also</span></span>  
 [<span data-ttu-id="64568-145">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="64568-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
