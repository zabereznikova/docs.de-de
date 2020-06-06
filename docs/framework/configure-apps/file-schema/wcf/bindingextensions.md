---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: bd6aeb32e0994bceb9e56bcb1c6267f4cb64a5a4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73039147"
---
# \<bindingExtensions>

<span data-ttu-id="ccb76-101">Dieser Abschnitt aktiviert die Verwendung einer benutzerdefinierten Bindung für eine Computer- oder Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ccb76-101">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="ccb76-102">Sie können eine benutzerdefinierte Bindung zur Auflistung hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf eine benutzerdefinierte Bindung sowie das `name`-Attribut auf den Namen der benutzerdefinierten Bindung festlegen.</span><span class="sxs-lookup"><span data-stu-id="ccb76-102">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>

<span data-ttu-id="ccb76-103">Bindungserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Bindungen als Teil einer Endpunktkonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccb76-103">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="ccb76-104">Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.Binding> implementiert.</span><span class="sxs-lookup"><span data-stu-id="ccb76-104">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>

<span data-ttu-id="ccb76-105">Im folgenden Beispiel wird das- `add` Element sowie das-Attribut verwendet, `name` um dem- `bindingExtensions` Abschnitt der Konfigurationsdatei eine Bindungs Erweiterung hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="ccb76-105">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingExtensions` section of the configuration file:</span></span>

```xml
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```

<span data-ttu-id="ccb76-106">Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingSection`-Element schreiben und registrieren.</span><span class="sxs-lookup"><span data-stu-id="ccb76-106">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="ccb76-107">Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ccb76-107">For more information on this, see the <xref:System.Configuration> documentation.</span></span>

<span data-ttu-id="ccb76-108">Nachdem das-Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung als Teil eines Endpunkts verwendet werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ccb76-108">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example:</span></span>

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a><span data-ttu-id="ccb76-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb76-109">See also</span></span>

- [<span data-ttu-id="ccb76-110">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ccb76-110">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
