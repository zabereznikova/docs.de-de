---
title: 'Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: e371c60e3fb674e4243cec008e1098172725d4cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937721"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="65a9a-102">Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="65a9a-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="65a9a-103">Sie können eine neue Einstellung zur Entwurfszeit erstellen, mit dem Einstellungs-Designer.</span><span class="sxs-lookup"><span data-stu-id="65a9a-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="65a9a-104">Der Einstellungs-Designer ist ein Raster-Style-Schnittstelle, mit dem Sie neue Einstellungen erstellen, und geben Sie Eigenschaften für diese Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="65a9a-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="65a9a-105">Sie müssen die Namen, Wert, Typ und Bereich für die neuen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="65a9a-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="65a9a-106">Sobald eine Einstellung erstellt wurde, ist es im Code zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="65a9a-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="65a9a-107">Zum Erstellen einer neuen Einstellung zur Entwurfszeit in C\#</span><span class="sxs-lookup"><span data-stu-id="65a9a-107">To create a new setting at design time in C\#</span></span>
  
1. <span data-ttu-id="65a9a-108">In **Projektmappen-Explorer**, erweitern Sie die **Eigenschaften** Knoten des Projekts.</span><span class="sxs-lookup"><span data-stu-id="65a9a-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2. <span data-ttu-id="65a9a-109">Doppelklicken Sie auf das Settings-Datei, in der Sie eine neue Einstellung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="65a9a-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="65a9a-110">Der Standardname für diese Datei ist Settings.settings.</span><span class="sxs-lookup"><span data-stu-id="65a9a-110">The default name for this file is Settings.settings.</span></span>  
  
3. <span data-ttu-id="65a9a-111">Legen Sie im Einstellungs-Designer den Namen, Wert, Typ und Bereich für Ihre Einstellung.</span><span class="sxs-lookup"><span data-stu-id="65a9a-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="65a9a-112">Jede Zeile stellt eine einzelne Einstellung dar.</span><span class="sxs-lookup"><span data-stu-id="65a9a-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="65a9a-113">Erstellen Sie eine neue Einstellung zur Entwurfszeit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65a9a-113">To create a new setting at design time in Visual Basic</span></span>  
  
1. <span data-ttu-id="65a9a-114">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="65a9a-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="65a9a-115">In der **Eigenschaften** Seite die **Einstellungen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="65a9a-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3. <span data-ttu-id="65a9a-116">Legen Sie im Einstellungs-Designer den Namen, Wert, Typ und Bereich für Ihre Einstellung.</span><span class="sxs-lookup"><span data-stu-id="65a9a-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="65a9a-117">Jede Zeile stellt eine einzelne Einstellung dar.</span><span class="sxs-lookup"><span data-stu-id="65a9a-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a9a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65a9a-118">See also</span></span>

- [<span data-ttu-id="65a9a-119">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="65a9a-119">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="65a9a-120">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="65a9a-120">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="65a9a-121">How To: Ändern Sie den Wert einer vorhandenen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="65a9a-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
