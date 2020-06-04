---
title: Fehlerhafter Dateimodus.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 534ea2d8316dc29cace798c5ad9b7697a290026f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409868"
---
# <a name="bad-file-mode"></a><span data-ttu-id="56171-102">Fehlerhafter Dateimodus.</span><span class="sxs-lookup"><span data-stu-id="56171-102">Bad file mode</span></span>
<span data-ttu-id="56171-103">Anweisungen, die zum Bearbeiten von Dateiinhalten verwendet werden, müssen für den Modus geeignet sein, in dem die Datei geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="56171-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="56171-104">Mögliche Ursachen sind:</span><span class="sxs-lookup"><span data-stu-id="56171-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="56171-105">Eine- `FilePutObject` oder- `FileGetObject` Anweisung gibt eine sequenzielle Datei an.</span><span class="sxs-lookup"><span data-stu-id="56171-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="56171-106">Eine- `Print` Anweisung gibt eine Datei an, die für einen anderen Zugriffsmodus als oder geöffnet wurde `Output` `Append` .</span><span class="sxs-lookup"><span data-stu-id="56171-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="56171-107">Eine- `Input` Anweisung gibt eine Datei an, die für einen anderen Zugriffsmodus geöffnet ist als`Input`</span><span class="sxs-lookup"><span data-stu-id="56171-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="56171-108">Der Versuch, in eine schreibgeschützte Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="56171-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="56171-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="56171-109">To correct this error</span></span>  
  
- <span data-ttu-id="56171-110">Stellen Sie `FilePutObject` sicher `FileGetObject` , dass und nur auf Dateien verweisen, die für den- `Random` oder- `Binary` Zugriff geöffnet</span><span class="sxs-lookup"><span data-stu-id="56171-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="56171-111">Stellen Sie sicher, `Print` dass eine Datei für `Output` den `Append` Zugriffsmodus oder geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="56171-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="56171-112">Wenn dies nicht der Wert ist, verwenden Sie eine andere Anweisung, um Daten in der Datei zu platzieren, oder öffnen Sie die Datei in einem entsprechenden Modus erneut.</span><span class="sxs-lookup"><span data-stu-id="56171-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="56171-113">Stellen Sie sicher, `Input` dass eine Datei für geöffnet ist `Input` .</span><span class="sxs-lookup"><span data-stu-id="56171-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="56171-114">Wenn dies nicht der Wert ist, verwenden Sie eine andere Anweisung, um Daten in der Datei zu platzieren, oder öffnen Sie die Datei in einem entsprechenden Modus</span><span class="sxs-lookup"><span data-stu-id="56171-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="56171-115">Wenn Sie in eine schreibgeschützte Datei schreiben, ändern Sie den Lese-/Schreibstatus der Datei, oder versuchen Sie nicht, in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="56171-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="56171-116">Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="56171-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56171-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56171-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="56171-118">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="56171-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
