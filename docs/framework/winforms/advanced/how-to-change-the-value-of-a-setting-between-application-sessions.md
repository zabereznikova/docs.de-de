---
title: 'Vorgehensweise: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318889"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Vorgehensweise: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen
In einigen Fällen empfiehlt es sich so ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde. Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge für die auf den richtigen Datenbankspeicherort zeigt zu ändern. Da Entwurfszeit-Tools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert manuell in der Datei ändern.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Zum Ändern des Werts einer Einstellung zwischen Anwendungssitzungen  
  
1. Mit Microsoft Notepad oder einige andere Text- oder XML-Editor, öffnen Sie die config-Datei Ihrer Anwendung zugeordnet.  
  
2. Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten. Es sollte etwa wie im folgenden Beispiel aussehen.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
