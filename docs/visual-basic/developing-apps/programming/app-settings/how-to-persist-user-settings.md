---
title: 'Vorgehensweise: Beibehalten von Benutzereinstellungen'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: 817111060259bdfbbb26d9f8eafeae439e1f651f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410152"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="817d3-102">Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="817d3-102">How to: Persist User Settings in Visual Basic</span></span>

<span data-ttu-id="817d3-103">Sie können mit der `My.Settings.Save`-Methode Änderungen der Benutzereinstellungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="817d3-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="817d3-104">Anwendungen werden üblicherweise so entwickelt, dass sie Änderungen der Benutzereinstellungen beibehalten, wenn die Anwendung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="817d3-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="817d3-105">Dies liegt daran, dass das Speichern der Einstellungen mehrere Sekunden in Anspruch nehmen kann; dabei hängt die Länge des Speichervorgangs von mehreren Faktoren ab.</span><span class="sxs-lookup"><span data-stu-id="817d3-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="817d3-106">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="817d3-106">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="817d3-107">Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="817d3-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="817d3-108">Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="817d3-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="817d3-109">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="817d3-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="817d3-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="817d3-110">Example</span></span>  

 <span data-ttu-id="817d3-111">In diesem Beispiel wird der Wert der Benutzereinstellung `LastChanged` geändert, und diese Änderung wird mit einem Aufruf an die `My.Settings.Save`-Methode gespeichert.</span><span class="sxs-lookup"><span data-stu-id="817d3-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 <span data-ttu-id="817d3-112">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `LastChanged`-Benutzereinstellung vom Typ `Date` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="817d3-112">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="817d3-113">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="817d3-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817d3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="817d3-114">See also</span></span>

- [<span data-ttu-id="817d3-115">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="817d3-115">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="817d3-116">How to: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="817d3-116">How to: Read Application Settings in Visual Basic</span></span>](how-to-read-application-settings.md)
- [<span data-ttu-id="817d3-117">How to: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="817d3-117">How to: Change User Settings in Visual Basic</span></span>](how-to-change-user-settings.md)
- [<span data-ttu-id="817d3-118">How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="817d3-118">How to: Create Property Grids for User Settings in Visual Basic</span></span>](how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="817d3-119">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="817d3-119">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
