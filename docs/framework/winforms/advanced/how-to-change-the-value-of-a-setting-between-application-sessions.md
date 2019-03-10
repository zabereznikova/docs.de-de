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
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="c634e-102">Vorgehensweise: Ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="c634e-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="c634e-103">In einigen Fällen empfiehlt es sich so ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c634e-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="c634e-104">Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge für die auf den richtigen Datenbankspeicherort zeigt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c634e-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="c634e-105">Da Entwurfszeit-Tools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert manuell in der Datei ändern.</span><span class="sxs-lookup"><span data-stu-id="c634e-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="c634e-106">Zum Ändern des Werts einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="c634e-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="c634e-107">Mit Microsoft Notepad oder einige andere Text- oder XML-Editor, öffnen Sie die config-Datei Ihrer Anwendung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c634e-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="c634e-108">Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c634e-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="c634e-109">Es sollte etwa wie im folgenden Beispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="c634e-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="c634e-110">Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="c634e-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c634e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c634e-111">See also</span></span>
- [<span data-ttu-id="c634e-112">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="c634e-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="c634e-113">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="c634e-113">Application Settings Overview</span></span>](application-settings-overview.md)
