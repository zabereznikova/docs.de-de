---
title: '&lt;bindingExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02f29ec698584ebe8b2ca1b5d438ac06ba6503b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltbindingextensionsgt"></a>&lt;bindingExtensions&gt;
Dieser Abschnitt aktiviert die Verwendung einer benutzerdefinierten Bindung für eine Computer- oder Anwendungskonfigurationsdatei. Sie können eine benutzerdefinierte Bindung zur Auflistung hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf eine benutzerdefinierte Bindung sowie das `name`-Attribut auf den Namen der benutzerdefinierten Bindung festlegen.  
  
 Bindungserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Bindungen als Teil einer Endpunktkonfiguration zu erstellen. Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.Binding> implementiert.  
  
 Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen einer Bindungserweiterung zum `bindingElementExtensions`-Abschnitt der Konfigurationsdatei verwendet.  
  
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
  
 Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingSection`-Element schreiben und registrieren. Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.  
  
 Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel dargestellt als Teil eines Endpunkts verwendet werden.  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
