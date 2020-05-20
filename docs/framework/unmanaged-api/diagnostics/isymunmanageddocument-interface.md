---
title: ISymUnmanagedDocument-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615565"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="bc039-102">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc039-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="bc039-103">Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bc039-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="bc039-104">Ein Dokument wird durch eine URL (Uniform Resource Serverlocatorpunkt) und eine Dokumenttyp-GUID definiert.</span><span class="sxs-lookup"><span data-stu-id="bc039-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="bc039-105">Sie können das Dokument unabhängig davon, wie es gespeichert wird, mithilfe der URL-und Dokumenttyp-GUID suchen.</span><span class="sxs-lookup"><span data-stu-id="bc039-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="bc039-106">Sie können die Dokument Quelle im Symbol Speicher speichern und über diese Schnittstelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="bc039-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc039-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc039-107">Methods</span></span>  
  
|<span data-ttu-id="bc039-108">Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-108">Method</span></span>|<span data-ttu-id="bc039-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc039-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc039-110">FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="bc039-111">Gibt die nächste Zeile zurück, bei der es sich um einen Sequenz Punkt handelt, bei dem eine Zeile in diesem Dokument angegeben ist, die ein Sequenz Punkt sein kann.</span><span class="sxs-lookup"><span data-stu-id="bc039-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="bc039-112">GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="bc039-113">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="bc039-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="bc039-114">GetCheckSumAlgorithmId-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="bc039-115">Ruft den Prüfsummen Algorithmus-Bezeichner ab oder gibt eine GUID aller Nullen zurück, wenn keine Prüfsumme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bc039-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="bc039-116">GetDocumentType-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="bc039-117">Ruft den Dokumenttyp dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="bc039-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="bc039-118">GetLanguage-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="bc039-119">Ruft den sprach Bezeichner für dieses Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="bc039-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="bc039-120">GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="bc039-121">Ruft den Hersteller der Sprache dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="bc039-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="bc039-122">GetSourceLength-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="bc039-123">Ruft die Länge der eingebetteten Quelle in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="bc039-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="bc039-124">GetSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="bc039-125">Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="bc039-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="bc039-126">GetURL-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="bc039-127">Gibt die URL für dieses Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="bc039-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="bc039-128">HasEmbeddedSource-Methode</span><span class="sxs-lookup"><span data-stu-id="bc039-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="bc039-129">Gibt zurück, `true` Wenn das Dokument in die Debugsymbole eingebettet ist; andernfalls wird zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="bc039-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc039-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc039-130">See also</span></span>

- [<span data-ttu-id="bc039-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc039-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
