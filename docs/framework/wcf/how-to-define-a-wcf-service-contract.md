---
title: 'Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5e8abbf8c5f9b0696d90ccbee94c5d8f4dd8b1ec
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809224"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="a1293-102">Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="a1293-102">How to: Define a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="a1293-103">Dies ist die erste von sechs Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a1293-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="a1293-104">Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="a1293-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="a1293-105">Wenn Sie einen WCF-Dienst zu erstellen, ist die erste Aufgabe zum Definieren eines Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="a1293-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="a1293-106">Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1293-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="a1293-107">Ein Vorgang ähnelt einer Webdienstmethode.</span><span class="sxs-lookup"><span data-stu-id="a1293-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="a1293-108">Verträge werden durch Definieren einer C++-, einer C#- oder einer Visual Basic (VB)-Schnittstelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1293-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="a1293-109">Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="a1293-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="a1293-110">Auf jede Schnittstelle muss das <xref:System.ServiceModel.ServiceContractAttribute> angewendet werden, und auf jeden Vorgang muss das <xref:System.ServiceModel.OperationContractAttribute> angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1293-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="a1293-111">Wenn eine Methode in einer Schnittstelle, die über das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut verfügt, nicht das <xref:System.ServiceModel.OperationContractAttribute>-Attribut aufweist, wird diese Methode vom Dienst nicht verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="a1293-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>  
  
 <span data-ttu-id="a1293-112">Der für diese Aufgabe verwendete Code wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a1293-112">The code used for this task is provided in the example following the procedure.</span></span>  
  
### <a name="to-define-a-service-contract"></a><span data-ttu-id="a1293-113">So definieren Sie einen Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="a1293-113">To define a service contract</span></span>  
  
1.  <span data-ttu-id="a1293-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] als Administrator, indem Sie mit der rechten Maustaste des Programms in der **starten** Menü- und Auswählen von **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a1293-114">Open  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as an administrator by right-clicking the program in the **Start** menu and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="a1293-115">Erstellen Sie einen WCF-Dienstbibliotheksprojekt, indem Sie auf die **Datei** Menü- und Auswählen von **neu**, **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a1293-115">Create a WCF Service Library project by clicking the **File** menu and selecting **New**, **Project**.</span></span> <span data-ttu-id="a1293-116">In der **neues Projekt** erweitern Sie im Dialogfeld auf der linken Seite des Dialogfelds **Visual C#-** für ein C#-Projekt oder **andere Sprachen** und dann **Visual Basic** für ein Visual Basic-Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1293-116">In the **New Project** dialog, on the left-hand side of the dialog expand **Visual C#** for a C# project or **Other Languages** and then **Visual Basic** for a Visual Basic project.</span></span> <span data-ttu-id="a1293-117">Wählen Sie unter der ausgewählten Sprache **WCF** und eine Liste der Projektvorlagen im mittleren Abschnitt des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1293-117">Under the language selected select **WCF** and a list of project templates will be displayed on the center section of the dialog.</span></span> <span data-ttu-id="a1293-118">Wählen Sie **WCF-Dienstbibliothek**, und geben `GettingStartedLib` in der **Namen** Textfeld und `GettingStarted` in der **Projektmappenname** Textfeld unten auf der das Dialogfeld ".</span><span class="sxs-lookup"><span data-stu-id="a1293-118">Select **WCF Service Library**, and type `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>  
  
3.  <span data-ttu-id="a1293-119">Visual Studio erstellt das Projekt, das 3 Dateien enthält: IService1.cs (oder IService1.vb),Service1.cs (oder Service1.vb) und App.config.  Die Datei IService1 enthält einen Standarddienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="a1293-119">Visual Studio will create the project which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config.  The IService1 file contains a default service contract.</span></span>  <span data-ttu-id="a1293-120">Die Datei Service1 enthält eine Standardimplementierung des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="a1293-120">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="a1293-121">Die Datei App.config enthält die Konfiguration, die erforderlich ist, um den Standarddienst mit dem Visual Studio-WCF-Diensthost zu laden.</span><span class="sxs-lookup"><span data-stu-id="a1293-121">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="a1293-122">Weitere Informationen zum WCF-Diensthost-Tool finden Sie unter [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="a1293-122">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>  
  
4.  <span data-ttu-id="a1293-123">Öffnen Sie die Datei IService1.cs oder IService1.vb, und löschen Sie den Code in der Namespacedeklaration, wobei Sie die Namespacedeklaration beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a1293-123">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration leaving the namespace declaration.</span></span> <span data-ttu-id="a1293-124">Definieren Sie in der Namespacedeklaration eine neue Schnittstelle mit dem Namen `ICalculator`, wie im Code unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a1293-124">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
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
  
    ```  
    ‘IService.vb  
    Imports System  
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
  
     <span data-ttu-id="a1293-125">Dieser Vertrag definiert einen Onlinerechner.</span><span class="sxs-lookup"><span data-stu-id="a1293-125">This contract defines an online calculator.</span></span> <span data-ttu-id="a1293-126">Beachten Sie, dass die `ICalculator`-Schnittstelle mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut markiert ist.</span><span class="sxs-lookup"><span data-stu-id="a1293-126">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="a1293-127">Dieses Attribut definiert einen Namespace, anhand dessen der Vertragsname eindeutig angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a1293-127">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="a1293-128">Jeder Rechnervorgang wird mit dem <xref:System.ServiceModel.OperationContractAttribute>-Attribut markiert.</span><span class="sxs-lookup"><span data-stu-id="a1293-128">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1293-129">Wenn eine Schnittstelle, ein Member oder eine Klasse mithilfe von Attributen mit Anmerkungen versehen wird, können Sie auf die Angabe „Attribute“ im Namen des Attributs verzichten.</span><span class="sxs-lookup"><span data-stu-id="a1293-129">When using attributes to annotate an interface, member, or class, you can drop the "Attribute" part from the attribute name.</span></span> <span data-ttu-id="a1293-130">Deshalb wird <xref:System.ServiceModel.ServiceContractAttribute> in C# zu `[ServiceContract]` oder in Visual Basic zu `<ServiceContract>`.</span><span class="sxs-lookup"><span data-stu-id="a1293-130">So <xref:System.ServiceModel.ServiceContractAttribute> becomes `[ServiceContract]` in C#, or `<ServiceContract>` in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1293-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1293-131">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="a1293-132">Vorgehensweise: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="a1293-132">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="a1293-133">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="a1293-133">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="a1293-134">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="a1293-134">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
