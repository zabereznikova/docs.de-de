---
title: Verwenden von Anwendungseinstellungen und Benutzereinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: f5231ecc9fb3898d60241ea8a53b509daced8a0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523841"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="8a464-102">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="8a464-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="8a464-103">Beginnend mit .NET Framework 2.0, können Sie erstellen und Zugriff auf Werte, die zwischen anwendungssitzungen-Ausführung beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="8a464-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="8a464-104">Diese Werte werden als bezeichnet *Einstellungen*.</span><span class="sxs-lookup"><span data-stu-id="8a464-104">These values are called *settings*.</span></span> <span data-ttu-id="8a464-105">Einstellungen können benutzereinstellungen darstellen, oder wertvoller Informationen, die Anwendung verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="8a464-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="8a464-106">Sie können z. B. eine Reihe von Einstellungen erstellen, die benutzereinstellungen für das Farbschema für eine Anwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8a464-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="8a464-107">Oder Sie können die Verbindungszeichenfolge, die eine Datenbank an, die von der Anwendung verwendeten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8a464-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="8a464-108">Einstellungen zulassen, dass Sie sowohl Informationen beibehalten, die für die Anwendung außerhalb des Codes und zum Erstellen von Profilen, die Einstellungen für die einzelnen Benutzern Speichern von entscheidender Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="8a464-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="8a464-109">Die Themen in diesem Abschnitt wird beschrieben, wie Einstellungen zur Entwurfszeit und Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="8a464-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a464-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8a464-110">In This Section</span></span>  
 [<span data-ttu-id="8a464-111">Gewusst wie: Erstellen einer neuen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="8a464-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="8a464-112">Es wird erläutert, wie Visual Studio verwenden, um eine neue Einstellung für eine Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a464-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="8a464-113">Gewusst wie: Ändern des Werts einer vorhandenen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="8a464-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="8a464-114">Beschreibt, wie Visual Studio verwenden, um den Wert einer vorhandenen Einstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a464-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="8a464-115">Gewusst wie: Ändern des Werts einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="8a464-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="8a464-116">Erläutert, wie Sie den Wert einer Einstellung in einer kompilierten Anwendung zwischen anwendungssitzungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a464-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="8a464-117">Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C#</span><span class="sxs-lookup"><span data-stu-id="8a464-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="8a464-118">Beschreibt, wie Code verwenden, um die Einstellungen mit den C#-gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="8a464-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="8a464-119">Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C#</span><span class="sxs-lookup"><span data-stu-id="8a464-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="8a464-120">Erläutert, wie Sie per Code schreiben, und speichern Sie die Werte der benutzereinstellungen für mit c#.</span><span class="sxs-lookup"><span data-stu-id="8a464-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="8a464-121">Gewusst wie: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#</span><span class="sxs-lookup"><span data-stu-id="8a464-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="8a464-122">Erläutert, wie Sie mehrere Sätze von Einstellungen zu einer Anwendung mit c# hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8a464-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a464-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a464-123">See Also</span></span>  
 [<span data-ttu-id="8a464-124">Anwendungseinstellungen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a464-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)
