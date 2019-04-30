---
title: 'Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929349"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="05597-102">Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="05597-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="05597-103">In diesem Tutorial wird die erste von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05597-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="05597-104">Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="05597-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="05597-105">Bei der Erstellung eines WCF-Diensts ist die erste Aufgabe, um einen Dienstvertrag zu definieren.</span><span class="sxs-lookup"><span data-stu-id="05597-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="05597-106">Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="05597-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="05597-107">Ein Vorgang ähnelt einer Webdienstmethode.</span><span class="sxs-lookup"><span data-stu-id="05597-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="05597-108">Sie erstellen Dienstverträge definieren eine Visualisierung C# oder Visual Basic (VB)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="05597-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="05597-109">Eine Schnittstelle weist folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="05597-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="05597-110">Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="05597-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="05597-111">Sie müssen für jede Schnittstelle, Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="05597-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="05597-112">Sie müssen für jede vorgangsmethode/Anwenden der <xref:System.ServiceModel.OperationContractAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="05597-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="05597-113">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="05597-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="05597-114">Erstellen Sie eine **WCF-Dienstbibliothek** Projekt.</span><span class="sxs-lookup"><span data-stu-id="05597-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="05597-115">Definieren Sie eine dienstvertragsschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="05597-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="05597-116">Erstellen Sie ein Projekt für die WCF-Dienstbibliothek und definieren eine dienstvertragsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="05597-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="05597-117">Öffnen Sie Visual Studio als Administrator.</span><span class="sxs-lookup"><span data-stu-id="05597-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="05597-118">Zu diesem Zweck wählen Sie das Visual Studio-Programm in der **starten** Menü, und wählen Sie dann **weitere** > **als Administrator ausführen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="05597-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="05597-119">Erstellen Sie eine **WCF-Dienstbibliothek** Projekt.</span><span class="sxs-lookup"><span data-stu-id="05597-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="05597-120">Wählen Sie im Menü **Datei** den Befehl **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="05597-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="05597-121">In der **neues Projekt** erweitern Sie im Dialogfeld auf der linken Seite **Visual C#-** oder **Visual Basic**, und wählen Sie dann die **WCF** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="05597-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="05597-122">Visual Studio zeigt eine Liste der Projektvorlagen im mittleren Abschnitt des Fensters.</span><span class="sxs-lookup"><span data-stu-id="05597-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="05597-123">Wählen Sie **WCF-Dienstbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="05597-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="05597-124">Wenn Sie nicht sehen die **WCF** Vorlagenkategorie Projekt müssen Sie möglicherweise installieren die **Windows Communication Foundation** Komponente von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05597-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="05597-125">In der **neues Projekt** wählen Sie im Dialogfeld die **Visual Studio-Installer öffnen** Link auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="05597-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="05597-126">Wählen Sie die **Einzelkomponenten** Registerkarte und suchen Sie dann aus, und wählen Sie **Windows Communication Foundation** unter der **Entwicklungsaktivitäten** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="05597-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="05597-127">Wählen Sie **ändern** zu beginnen, die Komponente zu installieren.</span><span class="sxs-lookup"><span data-stu-id="05597-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="05597-128">Geben Sie im unteren Bereich des Fensters ein, *GettingStartedLib* für die **Namen** und *GettingStarted* für die **Projektmappenname**.</span><span class="sxs-lookup"><span data-stu-id="05597-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="05597-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="05597-129">Select **OK**.</span></span>

      <span data-ttu-id="05597-130">Visual Studio erstellt das Projekt, das drei Dateien enthält: *IService1.cs* (oder *"IService1.vb"* für Visual Basic-Projekt), *Service1.cs* (oder *Service1.vb* für Visual Basic-Projekt), und  *Datei "App.config"*. Visual Studio werden diese Dateien wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="05597-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="05597-131">Die *IService1* -Datei enthält die Default-Definition des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="05597-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="05597-132">Die *"Service1"* -Datei enthält die standardmäßige Implementierung des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="05597-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="05597-133">Die *"App.config"* -Datei enthält die Konfigurationsinformationen, die erforderlich sind, um den Standarddienst mit dem Visual Studio-WCF-Diensthost-Tool zu laden.</span><span class="sxs-lookup"><span data-stu-id="05597-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="05597-134">Weitere Informationen zum Tool WCF-Diensthost finden Sie unter [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="05597-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="05597-135">Wenn Sie Visual Studio mit Visual Basic-entwicklereinstellungen Umgebung installiert haben, kann die Lösung ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="05597-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="05597-136">Wenn dies der Fall ist, wählen Sie **Optionen** aus der **Tools** Menü Wählen Sie dann **Projekte und Projektmappen** > **allgemeine** in die **Optionen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="05597-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="05597-137">Wählen Sie **Projektmappe immer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="05597-137">Select **Always show solution**.</span></span> <span data-ttu-id="05597-138">Darüber hinaus überprüfen Sie, ob **neue Projekte beim Erstellen speichern** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="05597-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="05597-139">Von **Projektmappen-Explorer**öffnen die **IService1.cs** oder **"IService1.vb"** Datei aus, und Ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="05597-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="05597-140">Dieser Vertrag definiert einen Onlinerechner.</span><span class="sxs-lookup"><span data-stu-id="05597-140">This contract defines an online calculator.</span></span> <span data-ttu-id="05597-141">Beachten Sie, dass die `ICalculator` Schnittstelle ist mit markiert die <xref:System.ServiceModel.ServiceContractAttribute> Attribut (als vereinfachte `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="05597-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="05597-142">Dieses Attribut definiert einen Namespace aus, um der Vertragsname eindeutig zu machen.</span><span class="sxs-lookup"><span data-stu-id="05597-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="05597-143">Der Code markiert jeder rechnervorgang wird mit der <xref:System.ServiceModel.OperationContractAttribute> Attribut (als vereinfachte `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="05597-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05597-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="05597-144">Next steps</span></span>

<span data-ttu-id="05597-145">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="05597-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="05597-146">Erstellen eines WCF-Dienstbibliothek-Projekts.</span><span class="sxs-lookup"><span data-stu-id="05597-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="05597-147">Definieren Sie eine dienstvertragsschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="05597-147">Define a service contract interface.</span></span>

<span data-ttu-id="05597-148">Fahren Sie fort mit dem nächsten Tutorial erfahren, wie die WCF-Dienstvertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="05597-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05597-149">Tutorial: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="05597-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
