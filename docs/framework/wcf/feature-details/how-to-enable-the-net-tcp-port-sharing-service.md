---
title: 'Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9934d198b8f3e30a4dc350c968263851ebeab1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="8157a-102">Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="8157a-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="8157a-103"> verwendet einen Windows-Dienst namens NET.TCP-Portfreigabedienst, der die gemeinsame Nutzung eines TCP-Anschlusses durch mehrere Prozesse vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="8157a-103"> uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="8157a-104">Dieser Dienst wird als Teil von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] installiert, ist jedoch aus Sicherheitsgründen nicht standardmäßig aktiviert. Daher muss er vor der ersten Verwendung manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8157a-104">This service is installed as part of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="8157a-105">In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="8157a-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="8157a-106">Nachdem Sie den Net.TCP-Portfreigabedienst aktivieren und starten Sie ihn manuell, finden Sie unter [Vorgehensweise: Konfigurieren eines WCF-Diensts, um die Portfreigabe verwenden](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) für Informationen dazu, wie Sie den Dienst zum Verwenden dieses Diensts konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8157a-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="8157a-107">Ein Beispiel, das net.tcp:// Portfreigabe verwendet, finden Sie unter der [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="8157a-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="8157a-108">So aktivieren Sie den Net.TCP-Portfreigabedienst mit MMC</span><span class="sxs-lookup"><span data-stu-id="8157a-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="8157a-109">Öffnen Sie über das Startmenü Diensteverwaltungskonsole, entweder indem Sie ein Eingabeaufforderungsfenster öffnen und Folgendes eingeben: `services.msc` oder durch Ausführen öffnen und Folgendes eingeben: `services.msc` in das Feld Öffnen.</span><span class="sxs-lookup"><span data-stu-id="8157a-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="8157a-110">In der **Namen** Maustaste Spalte der Liste der Dienste, die **Net.Tcp-Portfreigabedienst**, und wählen Sie **Eigenschaften** aus dem Menü.</span><span class="sxs-lookup"><span data-stu-id="8157a-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="8157a-111">So aktivieren Sie den manuellen Start des Diensts, in der **Eigenschaften** wählen Sie im Fenster der **allgemeine** Registerkarte, und klicken Sie in der **Starttyp** Feld wählen manuell, und klicken Sie dann auf **Gelten**.</span><span class="sxs-lookup"><span data-stu-id="8157a-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="8157a-112">Um den Dienst im Statusbereich Dienst zu starten, klicken Sie auf die **starten** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="8157a-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="8157a-113">Der Dienststatus sollte jetzt "Gestartet" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8157a-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="8157a-114">Um zu der Liste der Dienste zurückzukehren, klicken Sie auf die **OK**, und beenden Sie die MMC-Konsole.</span><span class="sxs-lookup"><span data-stu-id="8157a-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8157a-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8157a-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8157a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8157a-116">See Also</span></span>  
 [<span data-ttu-id="8157a-117">Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="8157a-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="8157a-118">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="8157a-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
