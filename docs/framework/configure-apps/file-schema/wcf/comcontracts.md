---
title: '&lt;comContracts&gt;'
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 26f17a331d69c38d720fcafe65c76f50c67def09
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150785"
---
# <a name="ltcomcontractsgt"></a><span data-ttu-id="65990-102">&lt;comContracts&gt;</span><span class="sxs-lookup"><span data-stu-id="65990-102">&lt;comContracts&gt;</span></span>
<span data-ttu-id="65990-103">Der `comContracts`-Konfigurationsabschnitt enthält Elemente, mit denen Sie verschiedene Eigenschaften eines COM+-Integrationsdienstvertrags angeben können.</span><span class="sxs-lookup"><span data-stu-id="65990-103">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="65990-104">Angeben von Namespace und Vertrag</span><span class="sxs-lookup"><span data-stu-id="65990-104">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="65990-105">COM+-integrationsdienstverträge sind aktuell auf beschränkt die `http://tempuri.org` -Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="65990-105">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="65990-106">Sie können Alternativen aber angeben, indem Sie den Abschnitt `comContracts` in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="65990-106">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="65990-107">Sie können z.&#160;B. folgende Konfiguration zum Angeben des Namespaces und Namens des Dienstvertrags sowie als Option zum Erzwingen sitzungsbasierter Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="65990-107">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="65990-108">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="65990-108">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="65990-109">Wenn dieser Abschnitt leer ist, wendet die Dienstinitialisierung einen standardmäßigen Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstellen-ID an.</span><span class="sxs-lookup"><span data-stu-id="65990-109">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="65990-110">Darüber hinaus können Sie die [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) -Element zum Angeben von COM+-Methoden, die bereitgestellt werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="65990-110">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="65990-111">Sie können auch die [ \<PersistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) dauerhaften Typen, die in der Integration an.</span><span class="sxs-lookup"><span data-stu-id="65990-111">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="65990-112">Verwenden Sie abschließend die [ \<UserDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) zum Angeben von benutzerdefinierten Typen (UDT), die in den Dienstvertrag eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="65990-112">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65990-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65990-113">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="65990-114">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="65990-114">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [<span data-ttu-id="65990-115">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="65990-115">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [<span data-ttu-id="65990-116">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="65990-116">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [<span data-ttu-id="65990-117">\<comContract></span><span class="sxs-lookup"><span data-stu-id="65990-117">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [<span data-ttu-id="65990-118">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="65990-118">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="65990-119">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="65990-119">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
