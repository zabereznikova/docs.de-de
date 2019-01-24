---
title: Verwenden von Anwendungseinstellungen und Benutzereinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: 70af7054353886757af81910f780e62001f0c9d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685112"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="c2746-102">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="c2746-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="c2746-103">Ab .NET Framework 2.0, können Sie erstellen und Zugriff auf Werte, die zwischen anwendungsausführungssitzungen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c2746-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="c2746-104">Diese Werte werden als bezeichnet *Einstellungen*.</span><span class="sxs-lookup"><span data-stu-id="c2746-104">These values are called *settings*.</span></span> <span data-ttu-id="c2746-105">Einstellungen können benutzereinstellungen darstellen, oder wertvolle Informationen, die Anwendung verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="c2746-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="c2746-106">Sie können z. B. eine Reihe von Einstellungen erstellen, die benutzereinstellungen für das Farbschema einer Anwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c2746-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="c2746-107">Oder Sie können die Verbindungszeichenfolge, die eine Datenbank angibt, die Ihre Anwendung verwendet möglicherweise speichern.</span><span class="sxs-lookup"><span data-stu-id="c2746-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="c2746-108">Einstellungen können, dass Sie sowohl Informationen beibehalten, die wichtig für die Anwendung außerhalb des Codes, und klicken Sie zum Erstellen von Profilen, in denen die Einstellungen einzelner Benutzer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="c2746-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="c2746-109">Die Themen in diesem Abschnitt wird beschrieben, wie Einstellungen zur Entwurfszeit und Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="c2746-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2746-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c2746-110">In This Section</span></span>  
 [<span data-ttu-id="c2746-111">How To: Erstellen einer neuen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="c2746-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="c2746-112">Erläutert, wie Sie Visual Studio verwenden, um eine neue Einstellung für eine Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2746-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="c2746-113">How To: Ändern Sie den Wert einer vorhandenen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="c2746-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="c2746-114">Beschreibt, wie Sie Visual Studio verwenden, um den Wert einer vorhandenen Einstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="c2746-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="c2746-115">How To: Ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="c2746-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="c2746-116">Enthält Informationen zum Ändern des Werts einer Einstellung in einer kompilierten Anwendung zwischen anwendungssitzungen.</span><span class="sxs-lookup"><span data-stu-id="c2746-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="c2746-117">How To: Lesen von Einstellungen zur Laufzeit mitC#</span><span class="sxs-lookup"><span data-stu-id="c2746-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="c2746-118">Beschreibt, wie Sie Code verwenden, um das Lesen von Einstellungen mit C#.</span><span class="sxs-lookup"><span data-stu-id="c2746-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="c2746-119">How To: Schreiben von Benutzereinstellungen zur Laufzeit mitC#</span><span class="sxs-lookup"><span data-stu-id="c2746-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="c2746-120">Erläutert die Verwendung von Code zu schreiben, und speichern Sie die Werte von benutzereinstellungen mit C#.</span><span class="sxs-lookup"><span data-stu-id="c2746-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="c2746-121">How To: Fügen Sie mehrerer Gruppen von Einstellungen zur Anwendung hinzuC#</span><span class="sxs-lookup"><span data-stu-id="c2746-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="c2746-122">Enthält Informationen zum Hinzufügen mehrerer Gruppen von Einstellungen auf eine Anwendung mit C#.</span><span class="sxs-lookup"><span data-stu-id="c2746-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2746-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2746-123">See also</span></span>
- [<span data-ttu-id="c2746-124">Anwendungseinstellungen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2746-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)
