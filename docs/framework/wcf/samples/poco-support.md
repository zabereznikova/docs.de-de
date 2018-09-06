---
title: POCO-Unterstützung
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: beba1469d5d9575a5b2ef76a4db3747dfcc35d0c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857601"
---
# <a name="poco-support"></a><span data-ttu-id="ba950-102">POCO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="ba950-102">POCO Support</span></span>
<span data-ttu-id="ba950-103">In diesem Beispiel wird die Serialisierungsunterstützung für makellose Typen demonstriert, d.&#160;h. Typen, auf die Serialisierungsattribute nicht angewendet wurden (diese werden auch als POCO-Typen (Plain Old CLR Object) bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="ba950-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="ba950-104">Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag für alle öffentlichen makellosen Typen ab, die über einen Standardkonstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="ba950-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a default constructor.</span></span> <span data-ttu-id="ba950-105">Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="ba950-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="ba950-106">Weitere Informationen zu nicht markierten Typen, finden Sie unter [serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba950-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="ba950-107">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), jedoch komplexe Zahlen anstelle primitiver numerischer Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba950-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="ba950-108">Es ähnelt auch der [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) Beispiel, außer dass die <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> Attribute werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba950-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="ba950-109">Der Dienst wird von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="ba950-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba950-110">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ba950-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ba950-111">Die `ComplexNumber`-Klasse wird im `ServiceContract` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba950-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="ba950-112">Der `ComplexNumber`-Typ verfügt nicht über das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ba950-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="ba950-113">Standardmäßig werden alle öffentlichen Eigenschaften und Felder serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ba950-113">By default, all public properties and fields are serialized.</span></span>  
  
```  
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ba950-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ba950-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ba950-115">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ba950-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ba950-116">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ba950-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ba950-117">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ba950-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba950-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ba950-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ba950-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ba950-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ba950-120">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ba950-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ba950-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ba950-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="ba950-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba950-122">See Also</span></span>  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [<span data-ttu-id="ba950-123">Serialisierbare Typen</span><span class="sxs-lookup"><span data-stu-id="ba950-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
