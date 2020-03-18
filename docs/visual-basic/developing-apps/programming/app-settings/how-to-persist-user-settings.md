---
title: 'Vorgehensweise: Beibehalten von Benutzereinstellungen'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: b1026e400015ff7807144dca8e9ce6d72fe3d18e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74329642"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="2861c-102">Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2861c-102">How to: Persist User Settings in Visual Basic</span></span>

<span data-ttu-id="2861c-103">Sie können mit der `My.Settings.Save`-Methode Änderungen der Benutzereinstellungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2861c-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="2861c-104">Anwendungen werden üblicherweise so entwickelt, dass sie Änderungen der Benutzereinstellungen beibehalten, wenn die Anwendung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2861c-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="2861c-105">Dies liegt daran, dass das Speichern der Einstellungen mehrere Sekunden in Anspruch nehmen kann; dabei hängt die Länge des Speichervorgangs von mehreren Faktoren ab.</span><span class="sxs-lookup"><span data-stu-id="2861c-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="2861c-106">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="2861c-106">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2861c-107">Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2861c-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="2861c-108">Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2861c-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="2861c-109">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2861c-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2861c-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2861c-110">Example</span></span>  

 <span data-ttu-id="2861c-111">In diesem Beispiel wird der Wert der Benutzereinstellung `LastChanged` geändert, und diese Änderung wird mit einem Aufruf an die `My.Settings.Save`-Methode gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2861c-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 <span data-ttu-id="2861c-112">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `LastChanged`-Benutzereinstellung vom Typ `Date` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2861c-112">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="2861c-113">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2861c-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2861c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2861c-114">See also</span></span>

- [<span data-ttu-id="2861c-115">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="2861c-115">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="2861c-116">How to: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2861c-116">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="2861c-117">How to: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2861c-117">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="2861c-118">How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2861c-118">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="2861c-119">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="2861c-119">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
