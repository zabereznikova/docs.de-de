---
title: 'Gewusst wie: Hinzufügen eines Datendienstverweises (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: a8dcc01fb7a564a363cabed6a22738cd520d317f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356230"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="ddd05-102">Gewusst wie: Hinzufügen eines Datendienstverweises (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ddd05-102">How to: Add a Data Service Reference (WCF Data Services)</span></span>
<span data-ttu-id="ddd05-103">Sie können die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio einen Verweis hinzufügen [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddd05-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="ddd05-104">Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln.</span><span class="sxs-lookup"><span data-stu-id="ddd05-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="ddd05-105">Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert.</span><span class="sxs-lookup"><span data-stu-id="ddd05-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="ddd05-106">Weitere Informationen finden Sie unter [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddd05-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>  
  
### <a name="to-add-a-data-service-reference"></a><span data-ttu-id="ddd05-107">So fügen Sie einen Datendienstverweis hinzu</span><span class="sxs-lookup"><span data-stu-id="ddd05-107">To add a data service reference</span></span>  
  
1.  <span data-ttu-id="ddd05-108">(Optional) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.</span><span class="sxs-lookup"><span data-stu-id="ddd05-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>  
  
2.  <span data-ttu-id="ddd05-109">Mit der rechten Maustaste des Clientprojekts, und wählen Sie dann **Hinzufügen eines Dienstverweises**.</span><span class="sxs-lookup"><span data-stu-id="ddd05-109">Right-click the client project and then select **Add Service Reference**.</span></span>  
  
3.  <span data-ttu-id="ddd05-110">Wenn der Datendienst Teil der aktuellen Projektmappe ist, klicken Sie auf **Discover**.</span><span class="sxs-lookup"><span data-stu-id="ddd05-110">If the data service is part of the current solution, click **Discover**.</span></span>  
  
     <span data-ttu-id="ddd05-111">- oder - </span><span class="sxs-lookup"><span data-stu-id="ddd05-111">-or-</span></span>  
  
     <span data-ttu-id="ddd05-112">In der **Adresse** Textfeld die base-URL des Datendiensts, z. B. `http://localhost:1234/Northwind.svc`, und klicken Sie dann auf **Go**.</span><span class="sxs-lookup"><span data-stu-id="ddd05-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>  
  
4.  <span data-ttu-id="ddd05-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddd05-113">Click **OK**.</span></span>  
  
     <span data-ttu-id="ddd05-114">Dadurch wird eine neue Codedatei hinzugefügt, die die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte +verwendeten Datenklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="ddd05-114">This adds a new code file that contains the data classes that are used to access and interact with data service resources as objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd05-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddd05-115">See Also</span></span>  
 [<span data-ttu-id="ddd05-116">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="ddd05-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
