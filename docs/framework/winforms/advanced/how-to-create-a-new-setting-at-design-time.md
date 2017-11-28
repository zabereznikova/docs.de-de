---
title: 'Gewusst wie: Erstellen einer neuen Einstellung zur Entwurfszeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e8a05b6f37f7686f18a6200e009aabe7eed5537
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="2f52c-102">Gewusst wie: Erstellen einer neuen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="2f52c-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="2f52c-103">Sie können eine neue Einstellung zur Entwurfszeit erstellen, mit dem Einstellungs-Designer.</span><span class="sxs-lookup"><span data-stu-id="2f52c-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="2f52c-104">Einstellungs-Designer ist ein Raster-Style-Schnittstelle, mit dem Sie neue Einstellungen erstellen und Eigenschaften für diese Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="2f52c-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="2f52c-105">Sie müssen Namen, Wert, Typ und Bereich für die neuen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="2f52c-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="2f52c-106">Sobald eine Einstellung erstellt wurde, ist es im Code zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f52c-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="2f52c-107">So erstellen eine neue Einstellung zur Entwurfszeit in c#</span><span class="sxs-lookup"><span data-stu-id="2f52c-107">To create a new setting at design time in C#</span></span>  
  
1.  <span data-ttu-id="2f52c-108">In **Projektmappen-Explorer**, erweitern Sie die **Eigenschaften** Knoten des Projekts.</span><span class="sxs-lookup"><span data-stu-id="2f52c-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="2f52c-109">Doppelklicken Sie auf der Settings-Datei, in der Sie eine neue Einstellung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="2f52c-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="2f52c-110">Der Standardname für diese Datei ist Settings.settings.</span><span class="sxs-lookup"><span data-stu-id="2f52c-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="2f52c-111">Legen Sie in der Einstellungs-Designer den Namen, Wert, Typ und Bereich für die Einstellung ein.</span><span class="sxs-lookup"><span data-stu-id="2f52c-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="2f52c-112">Jede Zeile stellt eine einzelne Einstellung.</span><span class="sxs-lookup"><span data-stu-id="2f52c-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="2f52c-113">So erstellen eine neue Einstellung zur Entwurfszeit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f52c-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="2f52c-114">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2f52c-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="2f52c-115">In der **Eigenschaften** Seite der **Einstellungen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="2f52c-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="2f52c-116">Legen Sie in der Einstellungs-Designer den Namen, Wert, Typ und Bereich für die Einstellung ein.</span><span class="sxs-lookup"><span data-stu-id="2f52c-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="2f52c-117">Jede Zeile stellt eine einzelne Einstellung.</span><span class="sxs-lookup"><span data-stu-id="2f52c-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f52c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f52c-118">See Also</span></span>  
 [<span data-ttu-id="2f52c-119">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="2f52c-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="2f52c-120">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="2f52c-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="2f52c-121">Gewusst wie: Ändern des Werts einer vorhandenen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="2f52c-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
