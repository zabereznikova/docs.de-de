---
title: "Gewusst wie: Ändern von Benutzereinstellungen in Visual Basic"
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
- user settings, changing in Visual Basic
- user settings
- My.Settings object, changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
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
ms.openlocfilehash: bfc5e5959d691e6a5f77fcffdb61c99bafa29aac
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="e6f54-102">Gewusst wie: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6f54-102">How to: Change User Settings in Visual Basic</span></span>
<span data-ttu-id="e6f54-103">Sie können eine Benutzereinstellung ändern, indem Sie der Einstellung der Eigenschaft auf dem `My.Settings`-Objekt einen neuen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e6f54-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="e6f54-104">Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e6f54-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="e6f54-105">Der Eigenschaftenname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e6f54-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="e6f54-106">Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="e6f54-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="e6f54-107">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="e6f54-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6f54-108">Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e6f54-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="e6f54-109">Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung mithilfe des **Projekt-Designers** erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e6f54-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="e6f54-110">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e6f54-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6f54-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6f54-111">Example</span></span>  
 <span data-ttu-id="e6f54-112">In diesem Beispiel wird der Wert der `Nickname`-Benutzereinstellung geändert.</span><span class="sxs-lookup"><span data-stu-id="e6f54-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 <span data-ttu-id="e6f54-113">[!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e6f54-113">[!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]</span></span>  
  
 <span data-ttu-id="e6f54-114">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Benutzereinstellung vom Typ `String` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e6f54-114">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="e6f54-115">Die Anwendung speichert die Benutzereinstellungen beim Herunterfahren der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e6f54-115">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="e6f54-116">Um die Einstellungen sofort zu speichern, rufen Sie die `My.Settings.Save`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="e6f54-116">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="e6f54-117">Weitere Informationen finden Sie unter [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e6f54-117">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f54-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6f54-118">See Also</span></span>  
 <span data-ttu-id="e6f54-119">[My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="e6f54-119">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="e6f54-120">[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="e6f54-120">[How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
 <span data-ttu-id="e6f54-121">[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="e6f54-121">[How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
 <span data-ttu-id="e6f54-122">[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="e6f54-122">[How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
 [<span data-ttu-id="e6f54-123">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="e6f54-123">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

