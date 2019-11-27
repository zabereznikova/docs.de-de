---
title: Ausführen von Aufgaben mit My.Application, My.Computer und My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: fc9fd9093a3db4785bfc94719dbae9ec1d586050
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329581"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="87a8b-102">Ausführen von Aufgaben mit My.Application, My.Computer und My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87a8b-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="87a8b-103">Die drei zentralen `My` Objekte, die Zugriff auf Informationen und häufig verwendete Funktionen bieten, sind `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) und `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="87a8b-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="87a8b-104">Sie können diese Objekte verwenden, um auf Informationen im Zusammenhang mit der aktuellen Anwendung, dem Computer, auf dem die Anwendung installiert ist, oder dem aktuellen Benutzer der Anwendung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="87a8b-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="87a8b-105">My. Application, My. Computer und My. User</span><span class="sxs-lookup"><span data-stu-id="87a8b-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="87a8b-106">In den folgenden Beispielen wird veranschaulicht, wie Informationen mithilfe von `My`abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="87a8b-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="87a8b-107">Zusätzlich zum Abrufen von Informationen ermöglichen die Elemente, die über diese drei Objekte verfügbar gemacht werden, auch das Ausführen von Methoden, die mit diesem Objekt verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="87a8b-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="87a8b-108">Beispielsweise können Sie auf eine Vielzahl von Methoden zugreifen, um Dateien zu bearbeiten oder die Registrierung über `My.Computer`zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="87a8b-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="87a8b-109">Datei-e/a ist mit `My`bedeutend einfacher und schneller, das eine Vielzahl von Methoden und Eigenschaften zum Bearbeiten von Dateien, Verzeichnissen und Laufwerken umfasst.</span><span class="sxs-lookup"><span data-stu-id="87a8b-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="87a8b-110">Das <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>-Objekt ermöglicht das Lesen aus großen strukturierten Dateien, die Felder mit Trennzeichen oder fester Breite enthalten.</span><span class="sxs-lookup"><span data-stu-id="87a8b-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="87a8b-111">In diesem Beispiel wird der `TextFieldParser` `reader` geöffnet und zum Lesen aus `C:\TestFolder1\test1.txt`verwendet.</span><span class="sxs-lookup"><span data-stu-id="87a8b-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="87a8b-112">mit `My.Application` können Sie die Kultur für Ihre Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="87a8b-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="87a8b-113">Im folgenden Beispiel wird veranschaulicht, wie diese Methode aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="87a8b-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="87a8b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87a8b-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="87a8b-115">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="87a8b-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
