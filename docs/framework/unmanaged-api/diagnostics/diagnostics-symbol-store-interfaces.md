---
title: Diagnosesymbolspeicher-Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787893"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="0a3d8-102">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0a3d8-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="0a3d8-103">In diesem Thema wird beschrieben, die nicht verwalteten Schnittstellen, mit denen einen Compiler Symbolinformationen für die Verwendung von einem Debugger zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a3d8-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0a3d8-104">In This Section</span></span>  
 [<span data-ttu-id="0a3d8-105">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="0a3d8-106">Enthält Methoden, die aktuelle Bindungsinformationen über die ausgeführte Anwendung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="0a3d8-107">IDebugAutoAttach-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="0a3d8-108">Definiert die Schnittstelle an, für eine AutoAttach-Debuggers.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="0a3d8-109">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="0a3d8-110">Deklariert Methoden, die für das Registrieren und Aufheben der Registrierung eine Benachrichtigung Verbindungsquelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="0a3d8-111">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="0a3d8-112">Deklariert Methoden, die für die Senke-Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="0a3d8-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="0a3d8-114">Deklariert eine Methode zum Festlegen von Benachrichtigung filtern.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="0a3d8-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="0a3d8-116">Enthält Informationen für die Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="0a3d8-117">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="0a3d8-118">Diese Schnittstelle ist die Ergänzung lesen [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0a3d8-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="0a3d8-119">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="0a3d8-120">Ermöglicht die Definition der optionalen Async-Methodeninformationen pro methodensymbol.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="0a3d8-121">Müssen mit einer geöffneten-Methode verwenden (d. h. zwischen den Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)und [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="0a3d8-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="0a3d8-122">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="0a3d8-123">Stellt einen Symbolbinder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="0a3d8-124">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="0a3d8-125">Stellt einen Symbolbinder für nicht verwalteten Code dar, und erweitert die `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="0a3d8-126">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="0a3d8-127">Stellt einen Symbolbinder für nicht verwalteten Code dar, und erweitert die `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="0a3d8-128">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="0a3d8-129">Bietet Zugriff auf nicht verwalteten Konstanten.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="0a3d8-130">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="0a3d8-131">Gibt nicht verwaltete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="0a3d8-132">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="0a3d8-133">Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="0a3d8-134">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="0a3d8-135">Stellt Methoden zum Schreiben in ein Dokument bereit, auf das ein Symbolspeicher verweist.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="0a3d8-136">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="0a3d8-137">Stellt Methoden für die Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="0a3d8-138">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="0a3d8-139">Stellt eine Methode in den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="0a3d8-140">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="0a3d8-141">Stellt einen Namespace dar.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="0a3d8-142">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="0a3d8-143">Stellt einen Symbolreader den Zugriff auf Dokumente, Methoden und Variablen in einem Symbolspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="0a3d8-144">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="0a3d8-145">Ruft ein Methodenobjekt des Symbolreaders erhält ein Methodentoken und eine Versionsnummer für bearbeiten und kopieren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="0a3d8-146">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="0a3d8-147">Bietet Methoden, die Symbolinformationen für die Suche zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="0a3d8-148">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="0a3d8-149">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="0a3d8-150">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="0a3d8-151">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode und erweitert die `ISymUnmanagedScope` Schnittstelle mit Methoden, die Informationen zu definierten Konstanten innerhalb des Bereichs abrufen...</span><span class="sxs-lookup"><span data-stu-id="0a3d8-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="0a3d8-152">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="0a3d8-153">Quelldaten für die Server bereitstellt für ein Modul.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="0a3d8-154">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="0a3d8-155">Enthält Methoden, die Informationen zu den Suchpfad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="0a3d8-156">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="0a3d8-157">Stellt eine Variable ein, z. B. ein Parameter, eine lokale Variable oder ein Feld dar.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="0a3d8-158">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="0a3d8-159">Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="0a3d8-160">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="0a3d8-161">Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="0a3d8-162">Erweitert die `ISymUnmanagedWriter` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="0a3d8-163">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="0a3d8-164">Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="0a3d8-165">Erweitert die `ISymUnmanagedWriter` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="0a3d8-166">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="0a3d8-167">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="0a3d8-168">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3d8-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="0a3d8-169">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0a3d8-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a3d8-170">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0a3d8-170">Related Sections</span></span>  
 [<span data-ttu-id="0a3d8-171">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0a3d8-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="0a3d8-172">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="0a3d8-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="0a3d8-173">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0a3d8-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
