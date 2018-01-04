---
title: "Gewusst wie: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c00e61001d9c8877b1fcaa0e938c92249c7915e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Gewusst wie: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen
In einigen Fällen empfiehlt es sich, ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde. Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge, zeigen Sie auf den richtigen Speicherort zu ändern. Da Entwurfszeittools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert in die Datei manuell ändern.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>So ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen  
  
1.  Öffnen Sie mit Microsoft Notepad oder ein anderer Text oder XML-Editor die config-Datei Ihrer Anwendung zugeordnet.  
  
2.  Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten. Es sollte ähnlich wie im folgenden Beispiel aussehen.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
