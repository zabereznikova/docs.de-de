---
title: ISymENCUnmanagedMethod-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441876"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="196c0-102">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="196c0-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="196c0-103">Enthält Informationen für das Feature "Bearbeiten und Fortfahren".</span><span class="sxs-lookup"><span data-stu-id="196c0-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="196c0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="196c0-104">Methods</span></span>  
  
|<span data-ttu-id="196c0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="196c0-105">Method</span></span>|<span data-ttu-id="196c0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="196c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="196c0-107">GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="196c0-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="196c0-108">Ruft die Dokumente ab, in denen diese Methode Zeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="196c0-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="196c0-109">GetDocumentsForMethodCount-Methode</span><span class="sxs-lookup"><span data-stu-id="196c0-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="196c0-110">Ruft die Anzahl der Dokumente ab, in denen diese Methode Zeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="196c0-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="196c0-111">GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="196c0-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="196c0-112">Ruft den Dateinamen für die Zeile ab, die einem Offset zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="196c0-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="196c0-113">GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="196c0-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="196c0-114">Ruft die einem Offset zugeordneten Zeilen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="196c0-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="196c0-115">GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="196c0-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="196c0-116">Ruft die kleinste anfangs Linie und die größte Endzeile für die Methode in einem bestimmten Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="196c0-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="196c0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="196c0-117">Requirements</span></span>  
 <span data-ttu-id="196c0-118">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="196c0-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="196c0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="196c0-119">See also</span></span>

- [<span data-ttu-id="196c0-120">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="196c0-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
