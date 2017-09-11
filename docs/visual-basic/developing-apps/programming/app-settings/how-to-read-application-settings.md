---
title: 'Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic'
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
- reading application settings
- My.Settings object, reading application settings
- application settings, reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
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
ms.openlocfilehash: e18c1da475ac7945a8bf080aad3ba2905d5d8658
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="3982b-102">Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3982b-102">How to: Read Application Settings in Visual Basic</span></span>
<span data-ttu-id="3982b-103">Sie können eine Benutzereinstellung lesen, indem Sie auf die Einstellung der Eigenschaft im `My.Settings`-Objekt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3982b-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="3982b-104">Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3982b-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="3982b-105">Der Eigenschaftsname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3982b-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="3982b-106">Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="3982b-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="3982b-107">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="3982b-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3982b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3982b-108">Example</span></span>  
 <span data-ttu-id="3982b-109">In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3982b-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="3982b-110">[!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3982b-110">[!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]</span></span>  
  
 <span data-ttu-id="3982b-111">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3982b-111">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="3982b-112">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="3982b-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3982b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3982b-113">See Also</span></span>  
 <span data-ttu-id="3982b-114">[My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="3982b-114">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="3982b-115">[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3982b-115">[How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
 <span data-ttu-id="3982b-116">[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3982b-116">[How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
 <span data-ttu-id="3982b-117">[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3982b-117">[How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
 [<span data-ttu-id="3982b-118">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="3982b-118">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

