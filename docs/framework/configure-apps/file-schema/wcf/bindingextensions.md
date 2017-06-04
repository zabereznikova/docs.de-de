---
title: "&lt;bindingExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;bindingExtensions&gt;
Dieser Abschnitt aktiviert die Verwendung einer benutzerdefinierten Bindung für eine Computer\- oder Anwendungskonfigurationsdatei.  Sie können eine benutzerdefinierte Bindung zur Auflistung hinzufügen, indem Sie das `add`\-Schlüsselwort verwenden und das `type`\-Attribut des Elements auf eine benutzerdefinierte Bindung sowie das `name`\-Attribut auf den Namen der benutzerdefinierten Bindung festlegen.  
  
 Bindungserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Bindungen als Teil einer Endpunktkonfiguration zu erstellen.  Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.Binding> implementiert.  
  
 Im folgenden Beispiel werden das `add`\-Element sowie das `name`\-Attribut zum Hinzufügen einer Bindungserweiterung zum `bindingElementExtensions`\-Abschnitt der Konfigurationsdatei verwendet.  
  
```  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingSection`\-Element schreiben und registrieren.  Weitere Informationen dazu finden Sie in der <xref:System.Configuration>\-Dokumentation.  
  
 Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel dargestellt als Teil eines Endpunkts verwendet werden.  
  
```  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
  
```  
  
## Siehe auch  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)