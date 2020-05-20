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
ms.openlocfilehash: 044ed5e08a85442c5a73c123cf51529d2fd3f1fc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442175"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="23bdf-102">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="23bdf-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="23bdf-103">In diesem Thema werden die nicht verwalteten Schnittstellen beschrieben, mit denen ein Compiler Symbol Informationen generieren kann, die von einem Debugger verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="23bdf-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23bdf-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="23bdf-104">In This Section</span></span>  
 [<span data-ttu-id="23bdf-105">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="23bdf-106">Stellt Methoden bereit, die aktuelle Bindungs Informationen zur ausgelaufenden Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="23bdf-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="23bdf-107">IDebugAutoAttach-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="23bdf-108">Definiert die Schnittstelle für eine vom Server aufgerufene automatische Debugger-Anfügung.</span><span class="sxs-lookup"><span data-stu-id="23bdf-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="23bdf-109">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="23bdf-110">Deklariert Methoden zum Registrieren und Aufheben der Registrierung einer Verbindungs Benachrichtigungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="23bdf-111">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="23bdf-112">Deklariert Methoden für Senke Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="23bdf-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="23bdf-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="23bdf-114">Deklariert eine Methode zum Festlegen von Benachrichtigungs filtern.</span><span class="sxs-lookup"><span data-stu-id="23bdf-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="23bdf-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="23bdf-116">Enthält Informationen für das Feature "Bearbeiten und Fortfahren".</span><span class="sxs-lookup"><span data-stu-id="23bdf-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="23bdf-117">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="23bdf-118">Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="23bdf-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="23bdf-119">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="23bdf-120">Ermöglicht die Definition Optionaler Async-Methoden Informationen pro Methoden Symbol.</span><span class="sxs-lookup"><span data-stu-id="23bdf-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="23bdf-121">Muss mit einer geöffneten Methode (d. h. zwischen Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)und der [CloseMethod-Methode](isymunmanagedwriter-closemethod-method.md)) verwenden.</span><span class="sxs-lookup"><span data-stu-id="23bdf-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="23bdf-122">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="23bdf-123">Stellt einen Symbol Binder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="23bdf-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="23bdf-124">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="23bdf-125">Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die- `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="23bdf-126">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="23bdf-127">Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die- `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="23bdf-128">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="23bdf-129">Ermöglicht den Zugriff auf nicht verwaltete Konstanten.</span><span class="sxs-lookup"><span data-stu-id="23bdf-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="23bdf-130">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="23bdf-131">Gibt nicht verwaltete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="23bdf-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="23bdf-132">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="23bdf-133">Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="23bdf-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="23bdf-134">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="23bdf-135">Stellt Methoden zum Schreiben in ein Dokument bereit, auf das ein Symbolspeicher verweist.</span><span class="sxs-lookup"><span data-stu-id="23bdf-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="23bdf-136">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="23bdf-137">Stellt Methoden für die Funktion "Bearbeiten und Fortfahren" bereit.</span><span class="sxs-lookup"><span data-stu-id="23bdf-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="23bdf-138">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="23bdf-139">Stellt eine Methode im Symbol Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="23bdf-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="23bdf-140">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="23bdf-141">Stellt einen Namespace dar.</span><span class="sxs-lookup"><span data-stu-id="23bdf-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="23bdf-142">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="23bdf-143">Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="23bdf-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="23bdf-144">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="23bdf-145">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="23bdf-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="23bdf-146">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="23bdf-147">Stellt Methoden bereit, die Symbol Suchinformationen erhalten.</span><span class="sxs-lookup"><span data-stu-id="23bdf-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="23bdf-148">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="23bdf-149">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="23bdf-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="23bdf-150">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="23bdf-151">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar und erweitert die- `ISymUnmanagedScope` Schnittstelle um Methoden, die Informationen zu Konstanten, die innerhalb des Bereichs definiert sind, erhalten.</span><span class="sxs-lookup"><span data-stu-id="23bdf-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="23bdf-152">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="23bdf-153">Stellt Quell Serverdaten für ein Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="23bdf-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="23bdf-154">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="23bdf-155">Stellt Methoden bereit, die Informationen über den Suchpfad erhalten.</span><span class="sxs-lookup"><span data-stu-id="23bdf-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="23bdf-156">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="23bdf-157">Stellt eine Variable dar, z. b. einen Parameter, eine lokale Variable oder ein Feld.</span><span class="sxs-lookup"><span data-stu-id="23bdf-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="23bdf-158">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="23bdf-159">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="23bdf-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="23bdf-160">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="23bdf-161">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="23bdf-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="23bdf-162">Erweitert die- `ISymUnmanagedWriter` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="23bdf-163">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="23bdf-164">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="23bdf-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="23bdf-165">Erweitert die- `ISymUnmanagedWriter` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="23bdf-166">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="23bdf-167">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="23bdf-168">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23bdf-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="23bdf-169">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23bdf-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="23bdf-170">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="23bdf-170">Related Sections</span></span>  
 [<span data-ttu-id="23bdf-171">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="23bdf-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="23bdf-172">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="23bdf-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="23bdf-173">Debuggen</span><span class="sxs-lookup"><span data-stu-id="23bdf-173">Debugging</span></span>](../debugging/index.md)
