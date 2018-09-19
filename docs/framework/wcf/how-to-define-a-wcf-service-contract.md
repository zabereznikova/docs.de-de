---
title: 'Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009007"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="a41d5-102">Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="a41d5-102">How to: Define a Windows Communication Foundation Service Contract</span></span>

<span data-ttu-id="a41d5-103">Dies ist der erste von sechs Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a41d5-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="a41d5-104">Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a41d5-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

 <span data-ttu-id="a41d5-105">Wenn Sie einen WCF-Dienst zu erstellen, ist die erste Aufgabe, um einen Dienstvertrag zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a41d5-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="a41d5-106">Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a41d5-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="a41d5-107">Ein Vorgang ähnelt einer Webdienstmethode.</span><span class="sxs-lookup"><span data-stu-id="a41d5-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="a41d5-108">Verträge werden durch Definieren einer C++-, einer C#- oder einer Visual Basic (VB)-Schnittstelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="a41d5-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="a41d5-109">Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="a41d5-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="a41d5-110">Auf jede Schnittstelle muss das <xref:System.ServiceModel.ServiceContractAttribute> angewendet werden, und auf jeden Vorgang muss das <xref:System.ServiceModel.OperationContractAttribute> angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a41d5-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="a41d5-111">Wenn eine Methode in einer Schnittstelle, die über das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut verfügt, nicht das <xref:System.ServiceModel.OperationContractAttribute>-Attribut aufweist, wird diese Methode vom Dienst nicht verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="a41d5-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>

 <span data-ttu-id="a41d5-112">Der für diese Aufgabe verwendete Code wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a41d5-112">The code used for this task is provided in the example following the procedure.</span></span>

## <a name="define-a-service-contract"></a><span data-ttu-id="a41d5-113">Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="a41d5-113">Define a service contract</span></span>

1. <span data-ttu-id="a41d5-114">Öffnen Sie Visual Studio als Administrator, indem Sie mit der rechten Maustaste in des Programms in der **starten** Menü und auswählen **weitere** > **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a41d5-114">Open Visual Studio as an administrator by right-clicking the program in the **Start** menu and selecting **More** > **Run as administrator**.</span></span>

2. <span data-ttu-id="a41d5-115">Erstellen eines WCF-Dienstbibliothek-Projekts.</span><span class="sxs-lookup"><span data-stu-id="a41d5-115">Create a WCF Service Library project.</span></span>

   1. <span data-ttu-id="a41d5-116">Wählen Sie im Menü **Datei** den Befehl **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="a41d5-116">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="a41d5-117">In der **neues Projekt** erweitern Sie im Dialogfeld auf der linken Seite **Visual C#-** oder **Visual Basic**, und wählen Sie dann die **WCF** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="a41d5-117">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="a41d5-118">Eine Liste der Projektvorlagen das Projekt wird im mittleren Abschnitt des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a41d5-118">A list of project templates is displayed in the center section of the dialog.</span></span> <span data-ttu-id="a41d5-119">Wählen Sie **WCF-Dienstbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="a41d5-119">Select **WCF Service Library**.</span></span>

   3. <span data-ttu-id="a41d5-120">Geben Sie `GettingStartedLib` in die **Namen** Textfeld und `GettingStarted` in die **Projektmappenname** Textfeld am unteren Rand des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="a41d5-120">Enter `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a41d5-121">Wenn Sie nicht sehen die **WCF** Vorlagenkategorie Projekt müssen Sie möglicherweise installieren die **Windows Communication Foundation** Komponente von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a41d5-121">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="a41d5-122">In der **neues Projekt** Dialogfeld klicken Sie auf den Link **Visual Studio-Installer öffnen**.</span><span class="sxs-lookup"><span data-stu-id="a41d5-122">In the **New Project** dialog box, click the link that says **Open Visual Studio Installer**.</span></span> <span data-ttu-id="a41d5-123">Wählen Sie die **Einzelkomponenten** Registerkarte und suchen Sie dann aus, und wählen Sie **Windows Communication Foundation** unter der **Entwicklungsaktivitäten** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="a41d5-123">Select the **Individual Components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="a41d5-124">Wählen Sie **ändern** zu beginnen, die Komponente zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a41d5-124">Choose **Modify** to begin installing the component.</span></span>

   <span data-ttu-id="a41d5-125">Visual Studio erstellt das Projekt, das 3 Dateien enthält: IService1.cs (oder "IService1.vb"), Service1.cs (oder Service1.vb) und "App.config". Die Datei IService1 enthält einen Standarddienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="a41d5-125">Visual Studio creates the project, which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config. The IService1 file contains a default service contract.</span></span> <span data-ttu-id="a41d5-126">Die Datei Service1 enthält eine Standardimplementierung des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="a41d5-126">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="a41d5-127">Die Datei App.config enthält die Konfiguration, die erforderlich ist, um den Standarddienst mit dem Visual Studio-WCF-Diensthost zu laden.</span><span class="sxs-lookup"><span data-stu-id="a41d5-127">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="a41d5-128">Weitere Informationen zum Tool WCF-Diensthost finden Sie unter [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="a41d5-128">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>

3. <span data-ttu-id="a41d5-129">Öffnen Sie die Datei IService1.cs oder IService1.vb, und löschen Sie den Code in der Namespacedeklaration, verlassen die Namespacedeklaration.</span><span class="sxs-lookup"><span data-stu-id="a41d5-129">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration, leaving the namespace declaration.</span></span> <span data-ttu-id="a41d5-130">Definieren Sie in der Namespacedeklaration eine neue Schnittstelle mit dem Namen `ICalculator`, wie im Code unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a41d5-130">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>

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

     <span data-ttu-id="a41d5-131">Dieser Vertrag definiert einen Onlinerechner.</span><span class="sxs-lookup"><span data-stu-id="a41d5-131">This contract defines an online calculator.</span></span> <span data-ttu-id="a41d5-132">Beachten Sie, dass die `ICalculator`-Schnittstelle mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut markiert ist.</span><span class="sxs-lookup"><span data-stu-id="a41d5-132">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="a41d5-133">Dieses Attribut definiert einen Namespace, anhand dessen der Vertragsname eindeutig angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a41d5-133">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="a41d5-134">Jeder Rechnervorgang wird mit dem <xref:System.ServiceModel.OperationContractAttribute>-Attribut markiert.</span><span class="sxs-lookup"><span data-stu-id="a41d5-134">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a41d5-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a41d5-135">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a41d5-136">Gewusst wie: implementieren ein Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="a41d5-136">How to: Implement a service contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a><span data-ttu-id="a41d5-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a41d5-137">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="a41d5-138">Vorgehensweise: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="a41d5-138">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="a41d5-139">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="a41d5-139">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="a41d5-140">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="a41d5-140">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)