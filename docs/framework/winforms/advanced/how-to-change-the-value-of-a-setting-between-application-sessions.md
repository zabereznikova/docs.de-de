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
ms.openlocfilehash: 2dff90e499ce421f372137903daf34c09c21d5c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="89701-102">Gewusst wie: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="89701-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="89701-103">In einigen Fällen empfiehlt es sich, ändern Sie den Wert einer Einstellung zwischen anwendungssitzungen, nachdem die Anwendung kompiliert und bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="89701-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="89701-104">Beispielsweise empfiehlt es sich um eine Verbindungszeichenfolge, zeigen Sie auf den richtigen Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89701-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="89701-105">Da Entwurfszeittools nicht verfügbar sind, nachdem die Anwendung kompiliert und bereitgestellt wurde, müssen Sie den Einstellungswert in die Datei manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="89701-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="89701-106">So ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="89701-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="89701-107">Öffnen Sie mit Microsoft Notepad oder ein anderer Text oder XML-Editor die config-Datei Ihrer Anwendung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="89701-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="89701-108">Suchen Sie den Eintrag für die Einstellung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="89701-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="89701-109">Es sollte ähnlich wie im folgenden Beispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="89701-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="89701-110">Geben Sie einen neuen Wert für die Einstellung aus, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="89701-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89701-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89701-111">See Also</span></span>  
 [<span data-ttu-id="89701-112">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="89701-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="89701-113">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="89701-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
