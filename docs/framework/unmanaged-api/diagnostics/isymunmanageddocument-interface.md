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
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449093"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="ba6eb-102">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba6eb-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="ba6eb-103">Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="ba6eb-104">Ein Dokument wird durch eine URL (Uniform Resource Serverlocatorpunkt) und eine Dokumenttyp-GUID definiert.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="ba6eb-105">Sie können das Dokument unabhängig davon, wie es gespeichert wird, mithilfe der URL-und Dokumenttyp-GUID suchen.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="ba6eb-106">Sie können die Dokument Quelle im Symbol Speicher speichern und über diese Schnittstelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba6eb-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="ba6eb-107">Methods</span></span>  
  
|<span data-ttu-id="ba6eb-108">Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-108">Method</span></span>|<span data-ttu-id="ba6eb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba6eb-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba6eb-110">FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="ba6eb-111">Gibt die nächste Zeile zurück, bei der es sich um einen Sequenz Punkt handelt, bei dem eine Zeile in diesem Dokument angegeben ist, die ein Sequenz Punkt sein kann.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="ba6eb-112">GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="ba6eb-113">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="ba6eb-114">GetCheckSumAlgorithmId-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="ba6eb-115">Ruft den Prüfsummen Algorithmus-Bezeichner ab oder gibt eine GUID aller Nullen zurück, wenn keine Prüfsumme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="ba6eb-116">GetDocumentType-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="ba6eb-117">Ruft den Dokumenttyp dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="ba6eb-118">GetLanguage-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="ba6eb-119">Ruft den sprach Bezeichner für dieses Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="ba6eb-120">GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="ba6eb-121">Ruft den Hersteller der Sprache dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="ba6eb-122">GetSourceLength-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="ba6eb-123">Ruft die Länge der eingebetteten Quelle in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="ba6eb-124">GetSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="ba6eb-125">Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="ba6eb-126">GetURL-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="ba6eb-127">Gibt die URL für dieses Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="ba6eb-128">HasEmbeddedSource-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6eb-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="ba6eb-129">Gibt `true` zurück, wenn das Dokument über eine in den Debugsymbolen eingebettete Quelle verfügt. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ba6eb-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba6eb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba6eb-130">See also</span></span>

- [<span data-ttu-id="ba6eb-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ba6eb-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
