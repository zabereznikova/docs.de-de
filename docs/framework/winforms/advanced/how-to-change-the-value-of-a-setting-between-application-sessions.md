---
title: 'Vorgehensweise: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 03a10e95362b1d49e4929c07ab6193f53898d34f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142856"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="04479-102">Vorgehensweise: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="04479-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="04479-103">In einigen Fällen empfiehlt es sich so ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="04479-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="04479-104">Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge für die auf den richtigen Datenbankspeicherort zeigt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="04479-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="04479-105">Da Entwurfszeit-Tools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert manuell in der Datei ändern.</span><span class="sxs-lookup"><span data-stu-id="04479-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="04479-106">Zum Ändern des Werts einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="04479-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="04479-107">Mit Microsoft Notepad oder einige andere Text- oder XML-Editor, öffnen Sie die config-Datei Ihrer Anwendung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="04479-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="04479-108">Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="04479-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="04479-109">Es sollte etwa wie im folgenden Beispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="04479-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="04479-110">Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="04479-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04479-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04479-111">See also</span></span>

- [<span data-ttu-id="04479-112">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="04479-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="04479-113">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="04479-113">Application Settings Overview</span></span>](application-settings-overview.md)
