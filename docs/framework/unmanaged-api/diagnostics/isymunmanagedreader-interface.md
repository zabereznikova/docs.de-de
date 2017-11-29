---
title: ISymUnmanagedReader-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="269d2-102">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="269d2-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="269d2-103">Stellt einen Symbolreader den Zugriff auf Dokumente, Methoden und Variablen in einem Symbolspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="269d2-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="269d2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="269d2-104">Methods</span></span>  
  
|<span data-ttu-id="269d2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-105">Method</span></span>|<span data-ttu-id="269d2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="269d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="269d2-107">GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="269d2-108">Sucht nach einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="269d2-108">Finds a document.</span></span>|  
|[<span data-ttu-id="269d2-109">GetDocuments-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="269d2-110">Gibt ein Array aller im Symbolspeicher definierten Dokumente.</span><span class="sxs-lookup"><span data-stu-id="269d2-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="269d2-111">GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="269d2-112">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="269d2-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="269d2-113">GetGlobalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="269d2-114">Gibt alle globale Variablen zurück.</span><span class="sxs-lookup"><span data-stu-id="269d2-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="269d2-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="269d2-116">Ruft ein Methodenobjekt des Symbolreaders, mit dem ein Token für die Methode ab.</span><span class="sxs-lookup"><span data-stu-id="269d2-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="269d2-117">GetMethodByVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="269d2-118">Ruft ein Methodenobjekt des Symbolreaders, erhält ein Methodentoken und eine Versionsnummer für bearbeiten und kopieren.</span><span class="sxs-lookup"><span data-stu-id="269d2-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="269d2-119">GetMethodFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="269d2-120">Gibt die Methode, die den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="269d2-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="269d2-121">GetMethodsFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="269d2-122">Gibt ein Array der Methoden, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="269d2-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="269d2-123">GetMethodVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="269d2-124">Ruft die Methodenversion ab.</span><span class="sxs-lookup"><span data-stu-id="269d2-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="269d2-125">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="269d2-126">Ruft die im globalen Gültigkeitsbereich in diesem Symbolspeicher definierten Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="269d2-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="269d2-127">GetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="269d2-128">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="269d2-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="269d2-129">GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="269d2-130">Enthält den Namen der Datei auf dem Datenträger für den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="269d2-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="269d2-131">GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="269d2-132">Gibt die Methode, die als benutzerdefinierter Einstiegspunkt für das Modul angegeben wurde zurück, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="269d2-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="269d2-133">GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="269d2-134">Zurückgeben einer nicht-lokalen Variablen aufgrund seiner übergeordneten und dem Namen.</span><span class="sxs-lookup"><span data-stu-id="269d2-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="269d2-135">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="269d2-136">Initialisiert den Symbolreader mit der Schnittstelle für die Metadaten, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.</span><span class="sxs-lookup"><span data-stu-id="269d2-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="269d2-137">ReplaceSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="269d2-138">Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="269d2-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="269d2-139">UpdateSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="269d2-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="269d2-140">Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="269d2-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="269d2-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="269d2-141">Requirements</span></span>  
 <span data-ttu-id="269d2-142">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="269d2-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269d2-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="269d2-143">See Also</span></span>  
 [<span data-ttu-id="269d2-144">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="269d2-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="269d2-145">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="269d2-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
