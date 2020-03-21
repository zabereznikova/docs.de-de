---
title: 'Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184091"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="c2b29-102">Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="c2b29-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="c2b29-103">In diesem Tutorial wird die erste von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c2b29-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c2b29-104">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c2b29-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c2b29-105">Wenn Sie einen WCF-Dienst erstellen, besteht Ihre erste Aufgabe darin, einen Servicevertrag zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c2b29-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="c2b29-106">Im Dienstvertrag ist angegeben, welche Vorgänge vom Dienst unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c2b29-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="c2b29-107">Ein Vorgang ähnelt einer Webdienstmethode.</span><span class="sxs-lookup"><span data-stu-id="c2b29-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="c2b29-108">Sie erstellen Serviceverträge, indem Sie eine C- oder Visual Basic-Schnittstelle definieren.</span><span class="sxs-lookup"><span data-stu-id="c2b29-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="c2b29-109">Eine Schnittstelle weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="c2b29-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="c2b29-110">Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="c2b29-110">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="c2b29-111">Für jede Schnittstelle müssen <xref:System.ServiceModel.ServiceContractAttribute> Sie das Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="c2b29-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="c2b29-112">Für jede Operation/Methode müssen <xref:System.ServiceModel.OperationContractAttribute> Sie das Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="c2b29-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="c2b29-113">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c2b29-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c2b29-114">Erstellen Sie ein **WCF-Dienstbibliotheksprojekt.**</span><span class="sxs-lookup"><span data-stu-id="c2b29-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="c2b29-115">Definieren Sie eine Servicevertragsschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2b29-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="c2b29-116">Erstellen eines WCF-Dienstbibliotheksprojekts und Definieren einer Servicevertragsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2b29-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="c2b29-117">Öffnen Sie Visual Studio als Administrator.</span><span class="sxs-lookup"><span data-stu-id="c2b29-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="c2b29-118">Wählen Sie dazu das Visual Studio-Programm im **Startmenü** aus, und wählen Sie dann im Kontextmenü **Mehr** > **Ausführen als Administrator** aus.</span><span class="sxs-lookup"><span data-stu-id="c2b29-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="c2b29-119">Erstellen Sie ein **WCF-Dienstbibliotheksprojekt.**</span><span class="sxs-lookup"><span data-stu-id="c2b29-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="c2b29-120">Klicken Sie im Menü **Datei** auf **Neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c2b29-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="c2b29-121">Erweitern Sie im Dialogfeld **Neues Projekt** auf der linken Seite Visual **C oder** Visual **Basic**, und wählen Sie dann die **WCF-Kategorie** aus.</span><span class="sxs-lookup"><span data-stu-id="c2b29-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="c2b29-122">Visual Studio zeigt eine Liste der Projektvorlagen im mittleren Bereich des Fensters an.</span><span class="sxs-lookup"><span data-stu-id="c2b29-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="c2b29-123">Wählen Sie **WCF-Dienstbibliothek**aus.</span><span class="sxs-lookup"><span data-stu-id="c2b29-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="c2b29-124">Wenn die **WCF-Projektvorlagenkategorie** nicht angezeigt wird, müssen Sie möglicherweise die Windows Communication **Foundation-Komponente** von Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="c2b29-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="c2b29-125">Wählen Sie im Dialogfeld **Neues Projekt** den Link Visual Studio **Installer öffnen** auf der linken Seite aus.</span><span class="sxs-lookup"><span data-stu-id="c2b29-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="c2b29-126">Wählen Sie die Registerkarte **Einzelne Komponenten** aus, und suchen Sie dann Windows **Communication Foundation** unter der Kategorie **Entwicklungsaktivitäten.**</span><span class="sxs-lookup"><span data-stu-id="c2b29-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="c2b29-127">Wählen Sie **Ändern** aus, um mit der Installation der Komponente zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c2b29-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="c2b29-128">Geben Sie im unteren Bereich des Fensters *GettingStartedLib* für den **Namen** und *GettingStarted* für den **Projektmappennamen**ein.</span><span class="sxs-lookup"><span data-stu-id="c2b29-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="c2b29-129">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="c2b29-129">Select **OK**.</span></span>

      <span data-ttu-id="c2b29-130">Visual Studio erstellt das Projekt mit drei Dateien: *IService1.cs* (oder *IService1.vb* für ein Visual Basic-Projekt), *Service1.cs* (oder *Service1.vb* für ein Visual Basic-Projekt) und *App.config*. Visual Studio definiert diese Dateien wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2b29-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="c2b29-131">Die *IService1-Datei* enthält die Standarddefinition des Servicevertrags.</span><span class="sxs-lookup"><span data-stu-id="c2b29-131">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="c2b29-132">Die *Service1-Datei* enthält die Standardimplementierung des Servicevertrags.</span><span class="sxs-lookup"><span data-stu-id="c2b29-132">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="c2b29-133">Die *Datei App.config* enthält die Konfigurationsinformationen, die zum Laden des Standarddienstes mit dem Visual Studio WCF-Diensthosttool erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c2b29-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="c2b29-134">Weitere Informationen zum WCF-Diensthosttool finden Sie unter [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c2b29-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c2b29-135">Wenn Sie Visual Studio mit den Visual Basic-Entwicklerumgebungseinstellungen installiert haben, ist die Lösung möglicherweise ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="c2b29-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="c2b29-136">Wenn dies der Fall ist, **wählen** Sie optionen aus dem Menü **Extras** und dann im Fenster **Optionen** die Option **Projekte und Lösungen** > **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="c2b29-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="c2b29-137">Wählen Sie **Immer Lösung anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c2b29-137">Select **Always show solution**.</span></span> <span data-ttu-id="c2b29-138">Überprüfen Sie außerdem, ob **neue Projekte beim Erstellen** speichern ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c2b29-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="c2b29-139">Öffnen Sie im **Projektmappen-Explorer**die **Datei IService1.cs** oder **IService1.vb,** und ersetzen Sie ihren Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c2b29-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="c2b29-140">Dieser Vertrag definiert einen Onlinerechner.</span><span class="sxs-lookup"><span data-stu-id="c2b29-140">This contract defines an online calculator.</span></span> <span data-ttu-id="c2b29-141">Beachten `ICalculator` Sie, dass <xref:System.ServiceModel.ServiceContractAttribute> die Schnittstelle `ServiceContract`mit dem Attribut (vereinfacht als ) gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="c2b29-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="c2b29-142">Dieses Attribut definiert einen Namespace, um den Vertragsnamen zu disambiguieren.</span><span class="sxs-lookup"><span data-stu-id="c2b29-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="c2b29-143">Der Code markiert jeden <xref:System.ServiceModel.OperationContractAttribute> Rechnervorgang mit `OperationContract`dem Attribut (vereinfacht als ).</span><span class="sxs-lookup"><span data-stu-id="c2b29-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c2b29-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c2b29-144">Next steps</span></span>

<span data-ttu-id="c2b29-145">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="c2b29-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c2b29-146">Erstellen Sie ein WCF-Dienstbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="c2b29-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="c2b29-147">Definieren Sie eine Servicevertragsschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2b29-147">Define a service contract interface.</span></span>

<span data-ttu-id="c2b29-148">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Servicevertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="c2b29-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c2b29-149">Tutorial: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="c2b29-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
