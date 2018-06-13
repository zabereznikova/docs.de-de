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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f75e517890275b90523dc42cdac3a83d871beac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427201"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="5f8b9-102">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f8b9-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="5f8b9-103">Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="5f8b9-104">Ein Dokument wird durch eine URL (uniform Resource Locator) und einen Dokumenttyp GUID definiert.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="5f8b9-105">Sie können das Dokument unabhängig davon, wie sie mithilfe der URL gespeichert werden und Dokumenttyp-GUID.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="5f8b9-106">Sie können die Quelle des Dokuments im Symbolspeicher gespeichert und über diese Schnittstelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f8b9-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="5f8b9-107">Methods</span></span>  
  
|<span data-ttu-id="5f8b9-108">Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-108">Method</span></span>|<span data-ttu-id="5f8b9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f8b9-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f8b9-110">FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="5f8b9-111">Gibt die nächste Zeile, die ein Sequenzpunkt ist, wobei eine angegebene Zeile in diesem Dokument, das nicht unbedingt ein Sequenzpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="5f8b9-112">GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="5f8b9-113">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="5f8b9-114">GetCheckSumAlgorithmId-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="5f8b9-115">Ruft den Bezeichner des Prüfsummenalgorithmus ab oder gibt eine GUID mit Nullen zurück, wenn keine Prüfsumme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="5f8b9-116">GetDocumentType-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="5f8b9-117">Ruft den Dokumenttyp dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="5f8b9-118">GetLanguage-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="5f8b9-119">Ruft die Sprachen-ID dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="5f8b9-120">GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="5f8b9-121">Ruft den Compilerhersteller dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="5f8b9-122">GetSourceLength-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="5f8b9-123">Ruft die Länge der eingebetteten Quelle in Byte ab.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="5f8b9-124">GetSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="5f8b9-125">Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="5f8b9-126">GetURL-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="5f8b9-127">Gibt die URL für dieses Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="5f8b9-128">HasEmbeddedSource-Methode</span><span class="sxs-lookup"><span data-stu-id="5f8b9-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="5f8b9-129">Gibt `true` , wenn das Dokument die Quelle in den Debugsymbolen; eingebettet ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f8b9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f8b9-130">See Also</span></span>  
 [<span data-ttu-id="5f8b9-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5f8b9-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
