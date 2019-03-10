---
title: 'Vorgehensweise: Ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: c1626cea581e5c180665d0ce805dea3e67f27a05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714358"
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
- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
