---
title: Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: bc2b0521598c00cdb398d936d61d65874a9cf274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583395"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="9f278-102">Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f278-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="9f278-103">Die drei wichtigsten `My` sind Objekte, die Zugriff auf Informationen und häufig verwendete Funktionen bereitstellen `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), und `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="9f278-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="9f278-104">Sie können diese Objekte verwenden, auf Informationen, die mit der aktuellen Anwendung, die Computer, dem auf die Anwendung installiert ist oder der aktuelle Benutzer der Anwendung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="9f278-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="9f278-105">My.Application, My.Computer und My.User</span><span class="sxs-lookup"><span data-stu-id="9f278-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="9f278-106">Die folgenden Beispiele zeigen Informationen wie möglich mit abgerufen `My`.</span><span class="sxs-lookup"><span data-stu-id="9f278-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="9f278-107">Zusätzlich zum Abrufen von Informationen ermöglichen die Elemente, die durch diese drei Objekte verfügbar gemacht werden darüber hinaus Methoden, die im Zusammenhang mit diesem Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9f278-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="9f278-108">Sie können z. B. eine Vielzahl von Methoden zum Bearbeiten von Dateien oder aktualisieren Sie die Registrierung über zugreifen `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="9f278-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="9f278-109">Datei-e/a ist deutlich einfacher und schneller mit `My`, darunter eine Vielzahl von Methoden und Eigenschaften zum Bearbeiten von Dateien, Verzeichnisse und Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="9f278-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="9f278-110">Die <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Objekts können Sie große strukturierte Dateien, die getrennt wurden oder Felder mit fester Breite gelesen.</span><span class="sxs-lookup"><span data-stu-id="9f278-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="9f278-111">In diesem Beispiel wird die `TextFieldParser``reader` und verwendet ihn zum Auslesen `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="9f278-111">This example opens the `TextFieldParser``reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="9f278-112">`My.Application` können Sie die Kultur für die Anwendung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9f278-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="9f278-113">Im folgende Beispiel wird veranschaulicht, wie diese Methode aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f278-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9f278-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f278-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="9f278-115">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="9f278-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
