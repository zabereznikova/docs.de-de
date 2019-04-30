---
title: Fehlerhafter Dateimodus.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935238"
---
# <a name="bad-file-mode"></a><span data-ttu-id="05b05-102">Fehlerhafter Dateimodus.</span><span class="sxs-lookup"><span data-stu-id="05b05-102">Bad file mode</span></span>
<span data-ttu-id="05b05-103">Anweisungen, die verwendet werden, in das Bearbeiten des Dateiinhalts müssen in den Modus geeignet sein, in denen die Datei geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="05b05-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="05b05-104">Mögliche Ursachen sind:</span><span class="sxs-lookup"><span data-stu-id="05b05-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="05b05-105">Ein `FilePutObject` oder `FileGetObject` Anweisung gibt eine sequenzielle Datei.</span><span class="sxs-lookup"><span data-stu-id="05b05-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="05b05-106">Ein `Print` -Anweisung gibt eine Datei, die für einen Zugriffsmodus geöffnet sind, außer `Output` oder `Append`.</span><span class="sxs-lookup"><span data-stu-id="05b05-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="05b05-107">Ein `Input` -Anweisung gibt eine Datei, die für einen Zugriffsmodus geöffnet sind, anders als `Input`</span><span class="sxs-lookup"><span data-stu-id="05b05-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="05b05-108">Es wurde versucht, in eine schreibgeschützte Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="05b05-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05b05-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="05b05-109">To correct this error</span></span>  
  
- <span data-ttu-id="05b05-110">Stellen Sie sicher, dass `FilePutObject` und `FileGetObject` verweisen nur auf Dateien, die für geöffnet `Random` oder `Binary` Zugriff.</span><span class="sxs-lookup"><span data-stu-id="05b05-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="05b05-111">Stellen Sie sicher, dass `Print` gibt an, eine für eine geöffnete Datei `Output` oder `Append` Zugriffsmodus.</span><span class="sxs-lookup"><span data-stu-id="05b05-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="05b05-112">Wenn dies nicht der Fall ist, eine andere Anweisung verwenden, um Daten in der Datei zu platzieren, oder öffnen Sie die Datei in einem entsprechenden Modus erneut.</span><span class="sxs-lookup"><span data-stu-id="05b05-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="05b05-113">Stellen Sie sicher, dass `Input` gibt an, eine für die geöffnete Datei `Input`.</span><span class="sxs-lookup"><span data-stu-id="05b05-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="05b05-114">Wenn dies nicht der Fall ist, verwenden Sie eine andere Anweisung zum Hinzufügen von Daten in der Datei oder erneutes Öffnen der Datei in einem entsprechenden Modus.</span><span class="sxs-lookup"><span data-stu-id="05b05-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="05b05-115">Wenn Sie in einer schreibgeschützten Datei schreiben, ändern Sie den Lese-/Schreibzugriff-Status der Datei, oder versuchen Sie nicht, um darin schreiben.</span><span class="sxs-lookup"><span data-stu-id="05b05-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="05b05-116">Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="05b05-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b05-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05b05-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="05b05-118">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="05b05-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
