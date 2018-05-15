---
title: '&lt;bindingExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: f99b38ede66dbecb44f9e8e67f921943071672ca
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingextensionsgt"></a><span data-ttu-id="ba35d-102">&lt;bindingExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="ba35d-102">&lt;bindingExtensions&gt;</span></span>
<span data-ttu-id="ba35d-103">Dieser Abschnitt aktiviert die Verwendung einer benutzerdefinierten Bindung für eine Computer- oder Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ba35d-103">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="ba35d-104">Sie können eine benutzerdefinierte Bindung zur Auflistung hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf eine benutzerdefinierte Bindung sowie das `name`-Attribut auf den Namen der benutzerdefinierten Bindung festlegen.</span><span class="sxs-lookup"><span data-stu-id="ba35d-104">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="ba35d-105">Bindungserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Bindungen als Teil einer Endpunktkonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba35d-105">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="ba35d-106">Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.Binding> implementiert.</span><span class="sxs-lookup"><span data-stu-id="ba35d-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="ba35d-107">Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen einer Bindungserweiterung zum `bindingElementExtensions`-Abschnitt der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba35d-107">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="ba35d-108">Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingSection`-Element schreiben und registrieren.</span><span class="sxs-lookup"><span data-stu-id="ba35d-108">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="ba35d-109">Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ba35d-109">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="ba35d-110">Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel dargestellt als Teil eines Endpunkts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba35d-110">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba35d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba35d-111">See Also</span></span>  
 [<span data-ttu-id="ba35d-112">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ba35d-112">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
