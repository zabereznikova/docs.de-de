---
title: 'Vorgehensweise: Programmgesteuertes Schreiben von Diensten'
description: Hier erfahren Sie, wie Sie Dienste programmgesteuert schreiben, indem Sie die Vererbung und andere Infrastrukturelemente selbst einrichten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 9693e3d387f38319519ab04211d8219fe1e5dda1
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925708"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="8fc99-103">Vorgehensweise: Programmgesteuertes Schreiben von Diensten</span><span class="sxs-lookup"><span data-stu-id="8fc99-103">How to: Write Services Programmatically</span></span>
<span data-ttu-id="8fc99-104">Wenn Sie nicht die Projektvorlage Windows-Dienst verwenden möchten, können Sie durch Einrichten der Vererbung und anderer Infrastrukturelemente eigene Dienste schreiben.</span><span class="sxs-lookup"><span data-stu-id="8fc99-104">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="8fc99-105">Sobald Sie einen Dienst programmgesteuert erstellen, müssen sie mehrere Schritte ausführen, die andernfalls von der Vorlage behandelt würden:</span><span class="sxs-lookup"><span data-stu-id="8fc99-105">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
- <span data-ttu-id="8fc99-106">Sie müssen die Dienstklasse einrichten, damit sie von der <xref:System.ServiceProcess.ServiceBase>-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="8fc99-106">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
- <span data-ttu-id="8fc99-107">Sie müssen für das Dienstprojekt eine `Main`-Methode erstellen, von der die auszuführenden Dienste festgelegt werden. Des Weiteren muss von ihr die <xref:System.ServiceProcess.ServiceBase.Run%2A>-Methode für die Dienste aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8fc99-107">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
- <span data-ttu-id="8fc99-108">Sie müssen die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Prozedur und die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Prozedur überschreiben und den Code einfügen, den diese ausführen sollen.</span><span class="sxs-lookup"><span data-stu-id="8fc99-108">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="8fc99-109">So schreiben Sie einen Dienst programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="8fc99-109">To write a service programmatically</span></span>  
  
1. <span data-ttu-id="8fc99-110">Erstellen Sie ein leeres Projekt und einen Verweis auf die notwendigen Namespaces, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8fc99-110">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1. <span data-ttu-id="8fc99-111">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8fc99-111">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2. <span data-ttu-id="8fc99-112">Führen Sie auf der Registerkarte **.NET Framework** einen Bildlauf zu **System.dll** durch, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8fc99-112">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3. <span data-ttu-id="8fc99-113">Führen Sie einen Bildlauf zu **System.ServiceProcess.dll** durch, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8fc99-113">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4. <span data-ttu-id="8fc99-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fc99-114">Click **OK**.</span></span>  
  
2. <span data-ttu-id="8fc99-115">Fügen Sie eine Klasse hinzu, und konfigurieren Sie diese, damit sie von <xref:System.ServiceProcess.ServiceBase> erbt:</span><span class="sxs-lookup"><span data-stu-id="8fc99-115">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. <span data-ttu-id="8fc99-116">Konfigurieren Sie die Dienstklasse, indem Sie folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8fc99-116">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. <span data-ttu-id="8fc99-117">Erstellen Sie für die Klasse eine `Main`-Methode, und verwenden Sie diese zum Definieren des Diensts, den diese Klasse enthält. `userService1` ist der Name der Klasse:</span><span class="sxs-lookup"><span data-stu-id="8fc99-117">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. <span data-ttu-id="8fc99-118">Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode, und definieren Sie die Verarbeitung beim Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="8fc99-118">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. <span data-ttu-id="8fc99-119">Überschreiben sie alle anderen Methoden, für die Sie benutzerdefinierte Verarbeitung definieren möchten. Schreiben Sie Code, mit dem Sie bestimmen, welche Aktionen vom Dienst in den einzelnen Fällen ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fc99-119">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7. <span data-ttu-id="8fc99-120">Fügen Sie die für die Dienstanwendung erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fc99-120">Add the necessary installers for your service application.</span></span> <span data-ttu-id="8fc99-121">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="8fc99-121">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
8. <span data-ttu-id="8fc99-122">Erstellen Sie das Projekt, indem Sie im Menü **Erstellen** den Befehl **Projektmappe erstellen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="8fc99-122">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8fc99-123">Drücken Sie nicht F5, um das Projekt auszuführen. Dienstprojekte können auf diese Weise nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8fc99-123">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="8fc99-124">Erstellen Sie ein Setup-Projekt und die benutzerdefinierten Aktionen, um den Dienst zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8fc99-124">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="8fc99-125">Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8fc99-125">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="8fc99-126">Installieren Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="8fc99-126">Install the service.</span></span> <span data-ttu-id="8fc99-127">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fc99-127">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc99-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fc99-128">See also</span></span>

- [<span data-ttu-id="8fc99-129">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="8fc99-129">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="8fc99-130">How to: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="8fc99-130">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="8fc99-131">How to: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="8fc99-131">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="8fc99-132">How to: Protokollinformationen über Dienste</span><span class="sxs-lookup"><span data-stu-id="8fc99-132">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="8fc99-133">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="8fc99-133">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
