---
title: 'Vorgehensweise: Ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 475e57e8bfdd5f3296c6af0fb20a472c729ea75c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540714"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Vorgehensweise: Ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen
In einigen Fällen empfiehlt es sich so ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde. Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge für die auf den richtigen Datenbankspeicherort zeigt zu ändern. Da Entwurfszeit-Tools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert manuell in der Datei ändern.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Zum Ändern des Werts einer Einstellung zwischen Anwendungssitzungen  
  
1.  Mit Microsoft Notepad oder einige andere Text- oder XML-Editor, öffnen Sie die config-Datei Ihrer Anwendung zugeordnet.  
  
2.  Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten. Es sollte etwa wie im folgenden Beispiel aussehen.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
