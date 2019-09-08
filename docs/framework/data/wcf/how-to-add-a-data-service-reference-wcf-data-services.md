---
title: 'Vorgehensweise: Hinzufügen eines Datendienst Verweises (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 42d89cf87b5fe9bbdb229f10cd6a0e340d4c08fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790741"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="a8627-102">Vorgehensweise: Hinzufügen eines Datendienst Verweises (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a8627-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="a8627-103">Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einen Verweis auf WCF Data Services hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a8627-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="a8627-104">Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln.</span><span class="sxs-lookup"><span data-stu-id="a8627-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="a8627-105">Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert.</span><span class="sxs-lookup"><span data-stu-id="a8627-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="a8627-106">Weitere Informationen finden Sie unter [Erstellen der Datendienst-Client Bibliothek](generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a8627-106">For more information, see [Generating the Data Service Client Library](generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="a8627-107">Hinzufügen eines Datendienst Verweises</span><span class="sxs-lookup"><span data-stu-id="a8627-107">Add a data service reference</span></span>

1. <span data-ttu-id="a8627-108">(Optional) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.</span><span class="sxs-lookup"><span data-stu-id="a8627-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="a8627-109">Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Client Projekt, und wählen Sie dann**Dienst Verweis** **Hinzufügen** > aus.</span><span class="sxs-lookup"><span data-stu-id="a8627-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="a8627-110">Wenn der Datendienst Teil der aktuellen Lösung ist, klicken Sie auf **ermitteln**.</span><span class="sxs-lookup"><span data-stu-id="a8627-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="a8627-111">-oder-</span><span class="sxs-lookup"><span data-stu-id="a8627-111">-or-</span></span>

     <span data-ttu-id="a8627-112">Geben Sie im Textfeld **Adresse** die Basis-URL des Daten Dienstanbieter ein, `http://localhost:1234/Northwind.svc`z. b., und klicken Sie dann auf **Gehe**zu.</span><span class="sxs-lookup"><span data-stu-id="a8627-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="a8627-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8627-113">Select **OK**.</span></span>

     <span data-ttu-id="a8627-114">Eine neue Codedatei, die die Daten Klassen enthält, die auf Datendienst Ressourcen zugreifen und diese interagieren können, wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8627-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8627-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8627-115">See also</span></span>

- [<span data-ttu-id="a8627-116">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="a8627-116">Quickstart</span></span>](quickstart-wcf-data-services.md)
