---
title: 'Gewusst wie: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 383f72f223fb92170d16a9538c94e67825009abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523409"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="91d30-102">Gewusst wie: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="91d30-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="91d30-103">In einigen Fällen empfiehlt es sich, ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="91d30-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="91d30-104">Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge, zeigen Sie auf den richtigen Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="91d30-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="91d30-105">Da Entwurfszeittools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert in die Datei manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="91d30-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="91d30-106">So ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="91d30-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="91d30-107">Öffnen Sie mit Microsoft Notepad oder ein anderer Text oder XML-Editor die config-Datei Ihrer Anwendung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="91d30-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="91d30-108">Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="91d30-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="91d30-109">Es sollte ähnlich wie im folgenden Beispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="91d30-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="91d30-110">Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="91d30-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d30-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91d30-111">See Also</span></span>  
 [<span data-ttu-id="91d30-112">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="91d30-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="91d30-113">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="91d30-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
