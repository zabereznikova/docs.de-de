---
title: ISymUnmanagedReader-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: b372021fcda39d9973d96a9c39e93e38617887a6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615461"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="e554f-102">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e554f-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="e554f-103">Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e554f-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e554f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e554f-104">Methods</span></span>  
  
|<span data-ttu-id="e554f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-105">Method</span></span>|<span data-ttu-id="e554f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e554f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e554f-107">GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-107">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="e554f-108">Sucht ein Dokument.</span><span class="sxs-lookup"><span data-stu-id="e554f-108">Finds a document.</span></span>|  
|[<span data-ttu-id="e554f-109">GetDocuments-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-109">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="e554f-110">Gibt ein Array aller im Symbol Speicher definierten Dokumente zurück.</span><span class="sxs-lookup"><span data-stu-id="e554f-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="e554f-111">GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-111">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="e554f-112">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="e554f-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="e554f-113">GetGlobalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-113">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="e554f-114">Gibt alle globalen Variablen zurück.</span><span class="sxs-lookup"><span data-stu-id="e554f-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="e554f-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-115">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="e554f-116">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e554f-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="e554f-117">GetMethodByVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-117">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="e554f-118">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e554f-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="e554f-119">GetMethodFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-119">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="e554f-120">Gibt die Methode zurück, die den Breakpoint an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="e554f-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="e554f-121">GetMethodsFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-121">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="e554f-122">Gibt ein Array von-Methoden zurück, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="e554f-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="e554f-123">GetMethodVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-123">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="e554f-124">Ruft die Methoden Version ab.</span><span class="sxs-lookup"><span data-stu-id="e554f-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="e554f-125">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-125">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="e554f-126">Ruft die Namespaces ab, die im globalen Gültigkeitsbereich innerhalb dieses Symbol Speicher definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e554f-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="e554f-127">GetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-127">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="e554f-128">Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.</span><span class="sxs-lookup"><span data-stu-id="e554f-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="e554f-129">GetSymbolStoreFileName-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-129">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="e554f-130">Gibt den Dateinamen des Symbol Speicher auf dem Datenträger an.</span><span class="sxs-lookup"><span data-stu-id="e554f-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="e554f-131">GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-131">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="e554f-132">Gibt die Methode zurück, die ggf. als Benutzer Einstiegspunkt für das Modul angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e554f-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="e554f-133">GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-133">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="e554f-134">Gibt eine nicht lokale Variable zurück, wenn Ihr übergeordnetes Element und der Name angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e554f-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="e554f-135">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-135">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="e554f-136">Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="e554f-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="e554f-137">ReplaceSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-137">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="e554f-138">Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="e554f-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="e554f-139">UpdateSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="e554f-139">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="e554f-140">Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="e554f-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e554f-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e554f-141">Requirements</span></span>  
 <span data-ttu-id="e554f-142">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e554f-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e554f-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e554f-143">See also</span></span>

- [<span data-ttu-id="e554f-144">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e554f-144">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e554f-145">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e554f-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
