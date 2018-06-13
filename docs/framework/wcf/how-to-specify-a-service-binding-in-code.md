---
title: 'Vorgehensweise: Angeben einer Dienstbindung im Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: ad8986537d0132bf61fe9eb2da2a13f8789ee4ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499287"
---
# <a name="how-to-specify-a-service-binding-in-code"></a><span data-ttu-id="7e5d0-102">Vorgehensweise: Angeben einer Dienstbindung im Code</span><span class="sxs-lookup"><span data-stu-id="7e5d0-102">How to: Specify a Service Binding in Code</span></span>
<span data-ttu-id="7e5d0-103">In diesem Beispiel wird ein `ICalculator`-Vertrag für einen Rechnerdienst definiert, der Dienst wird in der `CalculatorService`-Klasse implementiert, und der Endpunkt wird im Code definiert. Dort ist angegeben, dass die <xref:System.ServiceModel.BasicHttpBinding>-Klasse vom Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="7e5d0-104">Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="7e5d0-105">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="7e5d0-106">Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="7e5d0-107">Eine Beschreibung der diesen Dienst mithilfe von Konfigurationselementen statt Code zu konfigurieren, finden Sie unter [wie: Angeben einer Dienstbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7e5d0-107">For a description of how to configure this service using configuration elements instead of code, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a><span data-ttu-id="7e5d0-108">So geben Sie im Code die Verwendung der BasicHttpBinding für den Dienst an</span><span class="sxs-lookup"><span data-stu-id="7e5d0-108">To specify in code to use the BasicHttpBinding for the service</span></span>  
  
1.  <span data-ttu-id="7e5d0-109">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-109">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  <span data-ttu-id="7e5d0-110">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-110">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  <span data-ttu-id="7e5d0-111">Erstellen Sie in der Hostanwendung eine Basisadresse für den Dienst und die Bindung, die mit dem Dienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-111">In the hosting application, create the base address for the service and the binding to use with the service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  <span data-ttu-id="7e5d0-112">Erstellen Sie den Host für den Dienst, fügen Sie den Endpunkt hinzu, und öffnen Sie den Host.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-112">Create the host for the service, add the endpoint, and then open the host.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="7e5d0-113">So ändern Sie die Standardwerte für die Bindungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="7e5d0-113">To modify the default values of the binding properties</span></span>  
  
1.  <span data-ttu-id="7e5d0-114">Um die Standardeigenschaftswerte der <xref:System.ServiceModel.BasicHttpBinding>-Klasse zu ändern, legen Sie den Eigenschaftswert für die Bindung auf den neuen Wert fest, bevor Sie den Host erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e5d0-114">To modify one of the default property values of the <xref:System.ServiceModel.BasicHttpBinding> class, set the property value on the binding to the new value before creating the host.</span></span> <span data-ttu-id="7e5d0-115">Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7e5d0-115">For example, to change the default open and close timeout values of 1 minute to 2 minutes, use the following.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7e5d0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e5d0-116">See Also</span></span>  
 [<span data-ttu-id="7e5d0-117">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7e5d0-117">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="7e5d0-118">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="7e5d0-118">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
