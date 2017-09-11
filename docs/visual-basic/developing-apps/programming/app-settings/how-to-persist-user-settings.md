---
title: 'Gewusst wie: Beibehalten von Benutzereinstellungen in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object, persisting user settings
- persistence, persisting user settings [Visual Basic]
- user settings, persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a5553acd031db7e9be9c87afaeba61aea9bb2111
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="d6593-102">Gewusst wie: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6593-102">How to: Persist User Settings in Visual Basic</span></span>
<span data-ttu-id="d6593-103">Sie können mit der `My.Settings.Save`-Methode Änderungen der Benutzereinstellungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d6593-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="d6593-104">Anwendungen werden üblicherweise so entwickelt, dass sie Änderungen der Benutzereinstellungen beibehalten, wenn die Anwendung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6593-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="d6593-105">Dies liegt daran, dass das Speichern der Einstellungen mehrere Sekunden in Anspruch nehmen kann; dabei hängt die Länge des Speichervorgangs von mehreren Faktoren ab.</span><span class="sxs-lookup"><span data-stu-id="d6593-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="d6593-106">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="d6593-106">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6593-107">Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d6593-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="d6593-108">Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d6593-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="d6593-109">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d6593-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6593-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6593-110">Example</span></span>  
 <span data-ttu-id="d6593-111">In diesem Beispiel wird der Wert der Benutzereinstellung `LastChanged` geändert, und diese Änderung wird mit einem Aufruf an die `My.Settings.Save`-Methode gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6593-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 <span data-ttu-id="d6593-112">[!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d6593-112">[!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]</span></span>  
  
 <span data-ttu-id="d6593-113">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `LastChanged`-Benutzereinstellung vom Typ `Date` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d6593-113">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="d6593-114">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d6593-114">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6593-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6593-115">See Also</span></span>  
 <span data-ttu-id="d6593-116">[My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="d6593-116">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="d6593-117">[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="d6593-117">[How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
 <span data-ttu-id="d6593-118">[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="d6593-118">[How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
 <span data-ttu-id="d6593-119">[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="d6593-119">[How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
 [<span data-ttu-id="d6593-120">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="d6593-120">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

