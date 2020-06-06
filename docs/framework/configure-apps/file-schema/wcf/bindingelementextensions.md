---
title: <bindingElementExtensions>
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: c323a65ace332d2ecd1e03330dddbe7ca17ff5bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926368"
---
# \<bindingElementExtensions>
<span data-ttu-id="69d52-101">Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="69d52-101">This section enables the use of a custom binding element from a machine or application configuration file.</span></span> <span data-ttu-id="69d52-102">Sie können ein benutzerdefiniertes Bindungselement zur Auflistung hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf eine Bindungselementerweiterung sowie das `name`-Attribut auf das benutzerdefinierte Bindungselement festlegen.</span><span class="sxs-lookup"><span data-stu-id="69d52-102">You can add a custom binding element to this collection by using the `add` keyword, and setting the `type` attribute of the element to a binding element extension, as well as the `name` attribute to the custom binding element.</span></span>  
  
 <span data-ttu-id="69d52-103">Bindungserweiterungen ermöglichen es dem Benutzer, eigene Bindungselemente als Teil von benutzerdefinierten Bindungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69d52-103">Binding extensions enable the user to create user-defined binding elements for use as part of custom bindings.</span></span> <span data-ttu-id="69d52-104">Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.BindingElement> implementiert.</span><span class="sxs-lookup"><span data-stu-id="69d52-104">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="69d52-105">In der Konfigurationsdatei wird der `bindingElementExtensions`-Abschnitt zum Definieren eines Erweiterungselements verwendet.</span><span class="sxs-lookup"><span data-stu-id="69d52-105">In the configuration file, the `bindingElementExtensions` section is used to define an extension element.</span></span>  
  
 <span data-ttu-id="69d52-106">Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen einer Bindungserweiterung zum `bindingElementExtensions`-Abschnitt der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="69d52-106">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingElementExtensions>
      <add name="udpTransport"
           type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingElementExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="69d52-107">Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingElementExtensionSection`-Element schreiben und registrieren.</span><span class="sxs-lookup"><span data-stu-id="69d52-107">To add configuration abilities to the element, the user needs to write and register a `bindingElementExtensionSection` element.</span></span> <span data-ttu-id="69d52-108">Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="69d52-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="69d52-109">Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel dargestellt als Teil einer benutzerdefinierten Bindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69d52-109">After the element and its configuration type are defined, the extension can be used as part of a custom binding as shown in the following example.</span></span>  
  
```xml  
<customBinding>
  <binding name="test2">
    <udpTransport />
    <binaryMessageEncoding maxReadPoolSize="211"
                           maxWritePoolSize="2132"
                           maxSessionSize="3141" />
  </binding>
</customBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="69d52-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69d52-110">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>
- [<span data-ttu-id="69d52-111">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="69d52-111">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
