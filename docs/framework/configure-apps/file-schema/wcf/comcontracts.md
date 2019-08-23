---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: d061d48374a8745dc61e1ca156e4fcbbccee5ef7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919472"
---
# <a name="comcontracts"></a><span data-ttu-id="17dbb-101">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="17dbb-101">\<comContracts></span></span>
<span data-ttu-id="17dbb-102">Der `comContracts`-Konfigurationsabschnitt enthält Elemente, mit denen Sie verschiedene Eigenschaften eines COM+-Integrationsdienstvertrags angeben können.</span><span class="sxs-lookup"><span data-stu-id="17dbb-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="17dbb-103">Angeben von Namespace und Vertrag</span><span class="sxs-lookup"><span data-stu-id="17dbb-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="17dbb-104">Com+-Integrations Dienstverträge sind zurzeit auf `http://tempuri.org` den Namespace beschränkt, und der Vertrags Name wird von der unterstützenden com-Schnittstelle abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="17dbb-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="17dbb-105">Sie können Alternativen aber angeben, indem Sie den Abschnitt `comContracts` in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="17dbb-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="17dbb-106">Sie können z.&#160;B. folgende Konfiguration zum Angeben des Namespaces und Namens des Dienstvertrags sowie als Option zum Erzwingen sitzungsbasierter Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="17dbb-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="17dbb-107">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="17dbb-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="17dbb-108">Wenn dieser Abschnitt leer ist, wendet die Dienstinitialisierung einen standardmäßigen Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstellen-ID an.</span><span class="sxs-lookup"><span data-stu-id="17dbb-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="17dbb-109">Darüber hinaus können Sie das [ \<exposedMethod](exposedmethod.md) -Element >-Element verwenden, um com+-Methoden anzugeben, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="17dbb-109">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="17dbb-110">Sie können auch die [ \<persistabletypes->](persistabletypes.md) verwenden, um dauerhafte Typen anzugeben, die bei der Integration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="17dbb-110">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="17dbb-111">Schließlich können Sie das [ \<UserDefinedType](userdefinedtype.md) -Element >-Element verwenden, um benutzerdefinierte Typen (User Defined Types, UDT) einzuschließen, die in den Dienstvertrag eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="17dbb-111">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17dbb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17dbb-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="17dbb-113">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="17dbb-113">\<exposedMethod></span></span>](exposedmethod.md)
- [<span data-ttu-id="17dbb-114">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="17dbb-114">\<persistableTypes></span></span>](persistabletypes.md)
- [<span data-ttu-id="17dbb-115">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="17dbb-115">\<userDefinedType></span></span>](userdefinedtype.md)
- [<span data-ttu-id="17dbb-116">\<comContract></span><span class="sxs-lookup"><span data-stu-id="17dbb-116">\<comContract></span></span>](comcontract.md)
- [<span data-ttu-id="17dbb-117">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="17dbb-117">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="17dbb-118">Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen</span><span class="sxs-lookup"><span data-stu-id="17dbb-118">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
