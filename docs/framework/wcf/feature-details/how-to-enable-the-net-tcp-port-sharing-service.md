---
title: 'Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts'
description: Erfahren Sie, wie Sie den NET TCP-Port Freigabe Dienst mithilfe von MMC zum Aktivieren von "net. TCP" konfigurieren, das standardmäßig deaktiviert ist.
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 0292559e3befde7f0b00b36aa10a2d9615daf049
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246999"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="a1653-103">Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="a1653-103">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="a1653-104">Windows Communication Foundation (WCF) verwendet einen Windows-Dienst, der als net. TCP-Port Freigabe Dienst bezeichnet wird, um die Freigabe von TCP-Ports über mehrere Prozesse hinweg zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a1653-104">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="a1653-105">Dieser Dienst wird als Teil von WCF installiert, aber der Dienst ist nicht standardmäßig als Sicherheitsmaßnahme aktiviert und muss vor der ersten Verwendung manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a1653-105">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="a1653-106">In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="a1653-106">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="a1653-107">Nachdem Sie den Net. TCP-Port Freigabe Dienst aktiviert und manuell gestartet haben, finden Sie unter Gewusst [wie: Konfigurieren eines WCF-Dienstanbieter](how-to-configure-a-wcf-service-to-use-port-sharing.md) für die Verwendung von Port Freigabe Informationen zum Konfigurieren des Dienstanbieter für die Verwendung dieses Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="a1653-107">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="a1653-108">Ein Beispiel für die Verwendung von net. TCP://der Port Freigabe finden Sie unter [net. TCP-Port Freigabe Beispiel](../samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a1653-108">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="a1653-109">So aktivieren Sie den Net.TCP-Portfreigabedienst mit MMC</span><span class="sxs-lookup"><span data-stu-id="a1653-109">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="a1653-110">Öffnen Sie über das Startmenü die Dienste-Verwaltungskonsole, indem Sie ein Eingabe Aufforderungs Fenster öffnen und eingeben, `services.msc` oder indem Sie ausführen und `services.msc` in das Feld Öffnen eingeben.</span><span class="sxs-lookup"><span data-stu-id="a1653-110">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="a1653-111">Klicken Sie in der Spalte **Name** der Liste der Dienste mit der rechten Maustaste auf den **net. TCP-Port Freigabe Dienst**, und wählen Sie im Menü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a1653-111">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="a1653-112">Um das manuelle Starten des Dienstanbieter zu aktivieren, wählen Sie im **Eigenschaften** Fenster die Registerkarte **Allgemein** aus, und wählen Sie im Feld **Starttyp** die Option manuell aus, **und klicken Sie dann auf über**nehmen.</span><span class="sxs-lookup"><span data-stu-id="a1653-112">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="a1653-113">Um den Dienst zu starten, klicken Sie im Bereich Dienststatus auf die Schaltfläche **Start** .</span><span class="sxs-lookup"><span data-stu-id="a1653-113">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="a1653-114">Der Dienststatus sollte jetzt "Gestartet" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a1653-114">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="a1653-115">Um zur Liste der Dienste zurückzukehren, klicken Sie auf **OK**, und beenden Sie die MMC-Konsole.</span><span class="sxs-lookup"><span data-stu-id="a1653-115">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1653-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1653-116">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1653-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1653-117">See also</span></span>

- [<span data-ttu-id="a1653-118">Net.TCP-Anschlussfreigabe</span><span class="sxs-lookup"><span data-stu-id="a1653-118">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="a1653-119">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="a1653-119">Configuring the Net.TCP Port Sharing Service</span></span>](configuring-the-net-tcp-port-sharing-service.md)
