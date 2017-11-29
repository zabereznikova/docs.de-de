---
title: Zugreifen auf Anwendungsformulare (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b029ce984f9cef540087181a83070b0c8aa8132
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="d7712-102">Zugreifen auf Anwendungsformulare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7712-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="d7712-103">Mit dem `My.Forms`-Objekt können Sie ganz einfach auf eine Instanz von jedem Windows-Formular zugreifen, die im Projekt der Anwendung deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="d7712-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="d7712-104">Außerdem können Sie mit den Eigenschaften des `My.Application`-Objekts auf den Begrüßungsbildschirm und das Hauptformular der Anwendung zugreifen und eine Liste der offenen Formulare der Anwendung abrufen.</span><span class="sxs-lookup"><span data-stu-id="d7712-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="d7712-105">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d7712-105">Tasks</span></span>  
 <span data-ttu-id="d7712-106">Die folgende Tabelle enthält Beispiele zum Zugriff auf Anwendungsformate.</span><span class="sxs-lookup"><span data-stu-id="d7712-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="d7712-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7712-107">To</span></span>|<span data-ttu-id="d7712-108">Siehe</span><span class="sxs-lookup"><span data-stu-id="d7712-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="d7712-109">Zugreifen auf ein Formular von einem anderen Formular in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="d7712-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="d7712-110">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="d7712-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="d7712-111">Zeigen Sie die Titel der offenen Formulare aller Anwendungen an.</span><span class="sxs-lookup"><span data-stu-id="d7712-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="d7712-112">Aktualisieren Sie den Begrüßungsbildschirm mit Statusinformationen, während die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="d7712-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="d7712-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7712-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>  
 [<span data-ttu-id="d7712-114">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="d7712-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
