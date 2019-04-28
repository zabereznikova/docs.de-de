---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 47a7d862cf85254f88373d582169ff421be2b5b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673289"
---
# <a name="comcontracts"></a><span data-ttu-id="c5630-101">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="c5630-101">\<comContracts></span></span>
<span data-ttu-id="c5630-102">Der `comContracts`-Konfigurationsabschnitt enthält Elemente, mit denen Sie verschiedene Eigenschaften eines COM+-Integrationsdienstvertrags angeben können.</span><span class="sxs-lookup"><span data-stu-id="c5630-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="c5630-103">Angeben von Namespace und Vertrag</span><span class="sxs-lookup"><span data-stu-id="c5630-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="c5630-104">COM+-integrationsdienstverträge sind aktuell auf beschränkt die `http://tempuri.org` -Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c5630-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="c5630-105">Sie können Alternativen aber angeben, indem Sie den Abschnitt `comContracts` in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5630-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="c5630-106">Sie können z.&amp;#160;B. folgende Konfiguration zum Angeben des Namespaces und Namens des Dienstvertrags sowie als Option zum Erzwingen sitzungsbasierter Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5630-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="c5630-107">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="c5630-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="c5630-108">Wenn dieser Abschnitt leer ist, wendet die Dienstinitialisierung einen standardmäßigen Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstellen-ID an.</span><span class="sxs-lookup"><span data-stu-id="c5630-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="c5630-109">Darüber hinaus können Sie die [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) -Element zum Angeben von COM+-Methoden, die bereitgestellt werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c5630-109">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="c5630-110">Sie können auch die [ \<PersistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) dauerhaften Typen, die in der Integration an.</span><span class="sxs-lookup"><span data-stu-id="c5630-110">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="c5630-111">Verwenden Sie abschließend die [ \<UserDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) zum Angeben von benutzerdefinierten Typen (UDT), die in den Dienstvertrag eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c5630-111">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5630-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5630-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="c5630-113">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="c5630-113">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)
- [<span data-ttu-id="c5630-114">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="c5630-114">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)
- [<span data-ttu-id="c5630-115">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="c5630-115">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)
- [<span data-ttu-id="c5630-116">\<comContract></span><span class="sxs-lookup"><span data-stu-id="c5630-116">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)
- [<span data-ttu-id="c5630-117">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="c5630-117">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="c5630-118">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c5630-118">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
