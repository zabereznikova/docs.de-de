---
title: Fehlerhafter Dateimodus.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a><span data-ttu-id="4e856-102">Fehlerhafter Dateimodus.</span><span class="sxs-lookup"><span data-stu-id="4e856-102">Bad file mode</span></span>
<span data-ttu-id="4e856-103">-Anweisungen in Bearbeiten des Dateiinhalts müssen in den Modus geeignet sein, in denen die Datei geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="4e856-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="4e856-104">Mögliche Ursachen sind:</span><span class="sxs-lookup"><span data-stu-id="4e856-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="4e856-105">Ein `FilePutObject` oder `FileGetObject` -Anweisung gibt eine sequenzielle Datei.</span><span class="sxs-lookup"><span data-stu-id="4e856-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="4e856-106">Ein `Print` -Anweisung gibt eine andere als für einen Zugriffsmodus geöffnete Datei `Output` oder `Append`.</span><span class="sxs-lookup"><span data-stu-id="4e856-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="4e856-107">Ein `Input` -Anweisung gibt eine Datei für einen Zugriffsmodus außer geöffnet`Input`</span><span class="sxs-lookup"><span data-stu-id="4e856-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="4e856-108">Fehler beim Schreiben in eine schreibgeschützte Datei.</span><span class="sxs-lookup"><span data-stu-id="4e856-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e856-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4e856-109">To correct this error</span></span>  
  
-   <span data-ttu-id="4e856-110">Stellen Sie sicher, dass `FilePutObject` und `FileGetObject` verweisen nur auf Dateien, die für `Random` oder `Binary` Zugriff.</span><span class="sxs-lookup"><span data-stu-id="4e856-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="4e856-111">Stellen Sie sicher, dass `Print` gibt an, eine für eine geöffnete Datei `Output` oder `Append` Zugriffsmodus.</span><span class="sxs-lookup"><span data-stu-id="4e856-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="4e856-112">Wenn dies nicht der Fall ist, verwenden Sie eine andere Anweisung Daten in der Datei zu speichern, oder erneutes Öffnen der Datei im entsprechenden Modus.</span><span class="sxs-lookup"><span data-stu-id="4e856-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="4e856-113">Stellen Sie sicher, dass `Input` gibt an, eine für die geöffnete Datei `Input`.</span><span class="sxs-lookup"><span data-stu-id="4e856-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="4e856-114">Wenn dies nicht der Fall ist, verwenden Sie eine andere Anweisung zum Hinzufügen von Daten in der Datei, oder öffnen die Datei im entsprechenden Modus.</span><span class="sxs-lookup"><span data-stu-id="4e856-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="4e856-115">Wenn Sie in eine schreibgeschützte Datei schreiben, ändern Sie den Lese-/Schreibzugriff Status der Datei, oder versuchen Sie nicht zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4e856-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="4e856-116">Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="4e856-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e856-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e856-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [<span data-ttu-id="4e856-118">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="4e856-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
