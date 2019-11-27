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
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448526"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="22b44-102">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="22b44-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="22b44-103">In diesem Thema werden die nicht verwalteten Schnittstellen beschrieben, mit denen ein Compiler Symbol Informationen generieren kann, die von einem Debugger verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="22b44-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22b44-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="22b44-104">In This Section</span></span>  
 [<span data-ttu-id="22b44-105">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="22b44-106">Stellt Methoden bereit, die aktuelle Bindungs Informationen zur ausgelaufenden Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="22b44-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="22b44-107">IDebugAutoAttach-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="22b44-108">Definiert die Schnittstelle für eine vom Server aufgerufene automatische Debugger-Anfügung.</span><span class="sxs-lookup"><span data-stu-id="22b44-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="22b44-109">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="22b44-110">Deklariert Methoden zum Registrieren und Aufheben der Registrierung einer Verbindungs Benachrichtigungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="22b44-111">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="22b44-112">Deklariert Methoden für Senke Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="22b44-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="22b44-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="22b44-114">Deklariert eine Methode zum Festlegen von Benachrichtigungs filtern.</span><span class="sxs-lookup"><span data-stu-id="22b44-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="22b44-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="22b44-116">Enthält Informationen für das Feature "Bearbeiten und Fortfahren".</span><span class="sxs-lookup"><span data-stu-id="22b44-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="22b44-117">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="22b44-118">Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="22b44-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="22b44-119">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="22b44-120">Ermöglicht die Definition Optionaler Async-Methoden Informationen pro Methoden Symbol.</span><span class="sxs-lookup"><span data-stu-id="22b44-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="22b44-121">Muss mit einer geöffneten Methode (d. h. zwischen Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)und der [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)) verwenden.</span><span class="sxs-lookup"><span data-stu-id="22b44-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="22b44-122">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="22b44-123">Stellt einen Symbol Binder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="22b44-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="22b44-124">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="22b44-125">Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die `ISymUnmanagedBinder`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="22b44-126">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="22b44-127">Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die `ISymUnmanagedBinder`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="22b44-128">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="22b44-129">Ermöglicht den Zugriff auf nicht verwaltete Konstanten.</span><span class="sxs-lookup"><span data-stu-id="22b44-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="22b44-130">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="22b44-131">Gibt nicht verwaltete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="22b44-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="22b44-132">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="22b44-133">Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="22b44-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="22b44-134">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="22b44-135">Stellt Methoden zum Schreiben in ein Dokument bereit, auf das ein Symbolspeicher verweist.</span><span class="sxs-lookup"><span data-stu-id="22b44-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="22b44-136">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="22b44-137">Stellt Methoden für die Funktion "Bearbeiten und Fortfahren" bereit.</span><span class="sxs-lookup"><span data-stu-id="22b44-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="22b44-138">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="22b44-139">Stellt eine Methode im Symbol Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="22b44-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="22b44-140">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="22b44-141">Stellt einen Namespace dar.</span><span class="sxs-lookup"><span data-stu-id="22b44-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="22b44-142">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="22b44-143">Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="22b44-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="22b44-144">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="22b44-145">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="22b44-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="22b44-146">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="22b44-147">Stellt Methoden bereit, die Symbol Suchinformationen erhalten.</span><span class="sxs-lookup"><span data-stu-id="22b44-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="22b44-148">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="22b44-149">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="22b44-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="22b44-150">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="22b44-151">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar und erweitert die `ISymUnmanagedScope`-Schnittstelle um Methoden, die Informationen zu konstanten erhalten, die innerhalb des Bereichs definiert sind.</span><span class="sxs-lookup"><span data-stu-id="22b44-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="22b44-152">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="22b44-153">Stellt Quell Serverdaten für ein Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="22b44-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="22b44-154">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="22b44-155">Stellt Methoden bereit, die Informationen über den Suchpfad erhalten.</span><span class="sxs-lookup"><span data-stu-id="22b44-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="22b44-156">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="22b44-157">Stellt eine Variable dar, z. b. einen Parameter, eine lokale Variable oder ein Feld.</span><span class="sxs-lookup"><span data-stu-id="22b44-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="22b44-158">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="22b44-159">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="22b44-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="22b44-160">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="22b44-161">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="22b44-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="22b44-162">Erweitert die `ISymUnmanagedWriter`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="22b44-163">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="22b44-164">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="22b44-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="22b44-165">Erweitert die `ISymUnmanagedWriter`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="22b44-166">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="22b44-167">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="22b44-168">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22b44-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="22b44-169">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22b44-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="22b44-170">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="22b44-170">Related Sections</span></span>  
 [<span data-ttu-id="22b44-171">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="22b44-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="22b44-172">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="22b44-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="22b44-173">Debuggen</span><span class="sxs-lookup"><span data-stu-id="22b44-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
