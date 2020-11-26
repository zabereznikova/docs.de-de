---
title: 'Vorgehensweise: Angeben einer Dienstbindung im Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 7cf54754661182dca1e91c75b158d9b0a34a1f5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236480"
---
# <a name="how-to-specify-a-service-binding-in-code"></a><span data-ttu-id="edba9-102">Vorgehensweise: Angeben einer Dienstbindung im Code</span><span class="sxs-lookup"><span data-stu-id="edba9-102">How to: Specify a Service Binding in Code</span></span>

<span data-ttu-id="edba9-103">In diesem Beispiel wird ein `ICalculator`-Vertrag für einen Rechnerdienst definiert, der Dienst wird in der `CalculatorService`-Klasse implementiert, und der Endpunkt wird im Code definiert. Dort ist angegeben, dass die <xref:System.ServiceModel.BasicHttpBinding>-Klasse vom Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="edba9-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="edba9-104">Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.</span><span class="sxs-lookup"><span data-stu-id="edba9-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="edba9-105">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="edba9-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="edba9-106">Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="edba9-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="edba9-107">Eine Beschreibung der Konfiguration dieses Dienstanbieter mithilfe von Konfigurationselementen anstelle von Code finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="edba9-107">For a description of how to configure this service using configuration elements instead of code, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a><span data-ttu-id="edba9-108">So geben Sie im Code die Verwendung der BasicHttpBinding für den Dienst an</span><span class="sxs-lookup"><span data-stu-id="edba9-108">To specify in code to use the BasicHttpBinding for the service</span></span>  
  
1. <span data-ttu-id="edba9-109">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="edba9-109">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="edba9-110">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="edba9-110">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. <span data-ttu-id="edba9-111">Erstellen Sie in der Hostanwendung eine Basisadresse für den Dienst und die Bindung, die mit dem Dienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="edba9-111">In the hosting application, create the base address for the service and the binding to use with the service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. <span data-ttu-id="edba9-112">Erstellen Sie den Host für den Dienst, fügen Sie den Endpunkt hinzu, und öffnen Sie den Host.</span><span class="sxs-lookup"><span data-stu-id="edba9-112">Create the host for the service, add the endpoint, and then open the host.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="edba9-113">So ändern Sie die Standardwerte für die Bindungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="edba9-113">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="edba9-114">Um die Standardeigenschaftswerte der <xref:System.ServiceModel.BasicHttpBinding>-Klasse zu ändern, legen Sie den Eigenschaftswert für die Bindung auf den neuen Wert fest, bevor Sie den Host erstellen.</span><span class="sxs-lookup"><span data-stu-id="edba9-114">To modify one of the default property values of the <xref:System.ServiceModel.BasicHttpBinding> class, set the property value on the binding to the new value before creating the host.</span></span> <span data-ttu-id="edba9-115">Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="edba9-115">For example, to change the default open and close timeout values of 1 minute to 2 minutes, use the following.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="edba9-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edba9-116">See also</span></span>

- [<span data-ttu-id="edba9-117">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="edba9-117">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="edba9-118">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="edba9-118">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
