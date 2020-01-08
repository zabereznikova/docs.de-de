---
title: 'Tutorial: Definieren eines Windows Communication Foundation Service-Vertrags'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 49526808a65b68c6df734bd7f3e76eff1e4a6bc5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338297"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="5cb50-102">Tutorial: Definieren eines Windows Communication Foundation Service-Vertrags</span><span class="sxs-lookup"><span data-stu-id="5cb50-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="5cb50-103">In diesem Tutorial werden die ersten von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5cb50-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="5cb50-104">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="5cb50-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="5cb50-105">Wenn Sie einen WCF-Dienst erstellen, besteht die erste Aufgabe darin, einen Dienstvertrag zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5cb50-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="5cb50-106">Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5cb50-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="5cb50-107">Ein Vorgang ähnelt einer Webdienstmethode.</span><span class="sxs-lookup"><span data-stu-id="5cb50-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="5cb50-108">Sie erstellen Dienstverträge, indem Sie C# eine-oder Visual Basic-Schnittstelle definieren.</span><span class="sxs-lookup"><span data-stu-id="5cb50-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="5cb50-109">Eine Schnittstelle verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="5cb50-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="5cb50-110">Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="5cb50-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="5cb50-111">Für jede Schnittstelle müssen Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="5cb50-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="5cb50-112">Für jeden Vorgang/jede Methode müssen Sie das <xref:System.ServiceModel.OperationContractAttribute>-Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="5cb50-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="5cb50-113">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="5cb50-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5cb50-114">Erstellen Sie ein **WCF-Dienst Bibliotheks** Projekt.</span><span class="sxs-lookup"><span data-stu-id="5cb50-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="5cb50-115">Definieren Sie eine Dienstvertragschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5cb50-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="5cb50-116">Erstellen eines WCF-Dienst Bibliotheks Projekts und Definieren einer Dienstvertrags Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cb50-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="5cb50-117">Öffnen Sie Visual Studio als Administrator.</span><span class="sxs-lookup"><span data-stu-id="5cb50-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="5cb50-118">Wählen Sie hierzu im **Startmenü** das Visual Studio-Programm aus, und wählen Sie im Kontextmenü **Weitere** > **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="5cb50-119">Erstellen Sie ein **WCF-Dienst Bibliotheks** Projekt.</span><span class="sxs-lookup"><span data-stu-id="5cb50-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="5cb50-120">Wählen Sie im Menü **Datei** den Befehl **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="5cb50-121">Erweitern Sie im Dialogfeld **Neues Projekt** auf der linken Seite die Option  **C# Visual** oder **Visual Basic**, und wählen Sie dann die Kategorie **WCF** aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="5cb50-122">Visual Studio zeigt eine Liste der Projektvorlagen im mittleren Abschnitt des Fensters an.</span><span class="sxs-lookup"><span data-stu-id="5cb50-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="5cb50-123">Wählen Sie **WCF-Dienst Bibliothek**aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="5cb50-124">Wenn die Kategorie **WCF** -Projektvorlage nicht angezeigt wird, müssen Sie möglicherweise die **Windows Communication Foundation** Komponente von Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="5cb50-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="5cb50-125">Wählen Sie im Dialogfeld **Neues Projekt** den Link **Visual Studio-Installer öffnen** auf der linken Seite aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="5cb50-126">Wählen Sie die Registerkarte **einzelne Komponenten** aus, suchen Sie nach **Windows Communication Foundation** unter der Kategorie **Entwicklungsaktivitäten** , und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="5cb50-127">Wählen Sie **ändern** aus, um die Installation der Komponente zu starten</span><span class="sxs-lookup"><span data-stu-id="5cb50-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="5cb50-128">Geben Sie im unteren Abschnitt des Fensters *gettingstartedlib* als **Name** und *GettingStarted* als Projektmappennameein.</span><span class="sxs-lookup"><span data-stu-id="5cb50-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="5cb50-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cb50-129">Select **OK**.</span></span>

      <span data-ttu-id="5cb50-130">Visual Studio erstellt das Projekt, das über drei Dateien verfügt *: IService1.cs* (oder *IService1. vb* für ein Visual Basic Projekt), *Service1.cs* (oder *Service1. vb* für ein Visual Basic Projekt) und *app. config*. Diese Dateien werden von Visual Studio wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="5cb50-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="5cb50-131">Die *IService1* -Datei enthält die Standard Definition des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="5cb50-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="5cb50-132">Die *Service1* -Datei enthält die Standard Implementierung des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="5cb50-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="5cb50-133">Die Datei " *app. config* " enthält die Konfigurationsinformationen, die erforderlich sind, um den Standard Dienst mit dem Visual Studio WCF-Dienst Host Tool zu laden.</span><span class="sxs-lookup"><span data-stu-id="5cb50-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="5cb50-134">Weitere Informationen zum WCF-Dienst Host Tool finden Sie unter [WCF-Dienst Host (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5cb50-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="5cb50-135">Wenn Sie Visual Studio mit Visual Basic Einstellungen für die Entwicklerumgebung installiert haben, ist die Projekt Mappe möglicherweise ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="5cb50-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="5cb50-136">Wenn dies der Fall ist, wählen Sie **im Menü Extras die** **Option Optionen** aus, und wählen Sie dann im Fenster **Optionen** die Option **Projekte und Projekt** Mappen > **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="5cb50-137">Wählen Sie Projekt Mappe **immer anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="5cb50-137">Select **Always show solution**.</span></span> <span data-ttu-id="5cb50-138">Vergewissern Sie sich außerdem, dass **neue Projekte beim Erstellen speichern** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="5cb50-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="5cb50-139">Öffnen Sie die Datei **IService1.cs** oder **IService1. vb** von **Projektmappen-Explorer**, und ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5cb50-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     <span data-ttu-id="5cb50-140">Dieser Vertrag definiert einen Onlinerechner.</span><span class="sxs-lookup"><span data-stu-id="5cb50-140">This contract defines an online calculator.</span></span> <span data-ttu-id="5cb50-141">Beachten Sie, dass die `ICalculator`-Schnittstelle mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut markiert ist (vereinfacht als `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="5cb50-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="5cb50-142">Dieses Attribut definiert einen Namespace, um den Vertrags Namen eindeutig zu machen.</span><span class="sxs-lookup"><span data-stu-id="5cb50-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="5cb50-143">Der Code markiert jeden Rechner Vorgang mit dem <xref:System.ServiceModel.OperationContractAttribute>-Attribut (vereinfacht als `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="5cb50-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5cb50-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5cb50-144">Next steps</span></span>

<span data-ttu-id="5cb50-145">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="5cb50-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5cb50-146">Erstellen Sie ein WCF-Dienst Bibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="5cb50-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="5cb50-147">Definieren Sie eine Dienstvertragschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5cb50-147">Define a service contract interface.</span></span>

<span data-ttu-id="5cb50-148">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Dienstvertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="5cb50-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5cb50-149">Tutorial: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="5cb50-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
