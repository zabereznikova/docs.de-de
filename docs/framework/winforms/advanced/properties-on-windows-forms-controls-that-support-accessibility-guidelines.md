---
title: "Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ca18b35b90b028054e68a0a14fecc819a6c20b9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="3de92-102">Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen</span><span class="sxs-lookup"><span data-stu-id="3de92-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="3de92-103">In der standard-Toolbox für Windows Forms-Steuerelemente unterstützen viele der Richtlinien für Eingabehilfen, einschließlich Verfügbarmachung des Tastaturfokus und das Verfügbarmachen von der Bildschirmelemente.</span><span class="sxs-lookup"><span data-stu-id="3de92-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="3de92-104">Vorausplanen für Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="3de92-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="3de92-105">Die Eigenschaften des Steuerelements können verwendet werden, um andere Richtlinien für Eingabehilfen unterstützen, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3de92-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="3de92-106">Darüber hinaus sollten Sie die Menüs verwenden, um Zugriff auf das Programmieren von Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3de92-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="3de92-107">Eigenschaft ""</span><span class="sxs-lookup"><span data-stu-id="3de92-107">Control Property</span></span>|<span data-ttu-id="3de92-108">Überlegungen für Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="3de92-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="3de92-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="3de92-109">AccessibleDescription</span></span>|<span data-ttu-id="3de92-110">Die Beschreibung ist z. B. die Bildschirmsprachausgabe Eingabehilfen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3de92-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="3de92-111">Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="3de92-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="3de92-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="3de92-112">AccessibleName</span></span>|<span data-ttu-id="3de92-113">Der Name, die an die Eingabehilfen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="3de92-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="3de92-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="3de92-114">AccessibleRole</span></span>|<span data-ttu-id="3de92-115">Beschreibt die Verwendung des Elements in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="3de92-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="3de92-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="3de92-116">TabIndex</span></span>|<span data-ttu-id="3de92-117">Erstellt einen logischen Navigationspfad über das Formular.</span><span class="sxs-lookup"><span data-stu-id="3de92-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="3de92-118">Es ist wichtig für Steuerelemente ohne systeminterne Bezeichnung, z. B. Textfelder, deren zugeordnete Bezeichnung, die in der Aktivierreihenfolge direkt vorangestellt haben.</span><span class="sxs-lookup"><span data-stu-id="3de92-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="3de92-119">Text</span><span class="sxs-lookup"><span data-stu-id="3de92-119">Text</span></span>|<span data-ttu-id="3de92-120">Verwenden Sie das Zeichen "&", um Zugriffstasten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3de92-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="3de92-121">Mithilfe von Zugriffsschlüsseln ist Teil der Bereitstellung von dokumentierten tastaturzugriffen auf Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3de92-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="3de92-122">Schriftgrad</span><span class="sxs-lookup"><span data-stu-id="3de92-122">Font Size</span></span>|<span data-ttu-id="3de92-123">Wenn der Schriftgrad nicht anpassbar ist, sollte klicken sie auf 10 Punkt oder größer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3de92-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="3de92-124">Sobald Schriftgrad des Formulars festgelegt ist, werden alle in das Formular anschließend hinzugefügten Steuerelemente dieselbe Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3de92-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="3de92-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="3de92-125">Forecolor</span></span>|<span data-ttu-id="3de92-126">Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbe der benutzereinstellungen auf dem Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3de92-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="3de92-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="3de92-127">Backcolor</span></span>|<span data-ttu-id="3de92-128">Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbe der benutzereinstellungen auf dem Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3de92-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="3de92-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="3de92-129">BackgroundImage</span></span>|<span data-ttu-id="3de92-130">Lassen Sie diese Eigenschaft leer, um Text besser lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="3de92-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3de92-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3de92-131">See Also</span></span>  
 [<span data-ttu-id="3de92-132">Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3de92-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
