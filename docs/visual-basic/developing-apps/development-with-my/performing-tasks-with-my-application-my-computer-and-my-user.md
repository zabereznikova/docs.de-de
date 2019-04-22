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
ms.openlocfilehash: 0372fbf63f6d12e266674f92225183911aa4ca30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834045"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="7e048-102">Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e048-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="7e048-103">Die drei wichtigsten `My` Objekte, die Zugriff auf Informationen und häufig verwendeten Funktionen bereitstellen, sind `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), und `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="7e048-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="7e048-104">Sie können diese Objekte verwenden, auf Informationen, die mit der aktuellen Anwendung, die Computer, dem auf die Anwendung installiert ist oder der aktuelle Benutzer der Anwendung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="7e048-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="7e048-105">My.Application, My.Computer und My.User</span><span class="sxs-lookup"><span data-stu-id="7e048-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="7e048-106">Die folgenden Beispiele zeigen Informationen wie möglich mit abgerufen `My`.</span><span class="sxs-lookup"><span data-stu-id="7e048-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="7e048-107">Zusätzlich zum Abrufen von Informationen, können die Elemente, die über diese drei Objekte verfügbar gemacht werden auch, Sie Methoden, die im Zusammenhang mit diesem Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7e048-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="7e048-108">Sie können z. B. eine Vielzahl von Methoden zum Bearbeiten von Dateien oder aktualisieren Sie die Registrierung über zugreifen `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="7e048-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="7e048-109">Datei-e/a ist bedeutend einfacher und schneller mit `My`, wozu eine Vielzahl von Methoden und Eigenschaften zum Bearbeiten von Dateien, Verzeichnisse und Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="7e048-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="7e048-110">Die <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Objekt ermöglicht Ihnen das Lesen von großen strukturierten Dateien, die getrennt wurden oder Felder mit fester Breite.</span><span class="sxs-lookup"><span data-stu-id="7e048-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="7e048-111">In diesem Beispiel öffnet der `TextFieldParser` `reader` und verwendet ihn zum Lesen aus `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="7e048-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="7e048-112">`My.Application` können Sie die Kultur für Ihre Anwendung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7e048-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="7e048-113">Im folgende Beispiel wird veranschaulicht, wie diese Methode aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e048-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7e048-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e048-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="7e048-115">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="7e048-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
