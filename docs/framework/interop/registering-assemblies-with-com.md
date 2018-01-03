---
title: Registrieren von Assemblys mit COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1473fa07b57dcd19ea192db6cdb0a395f119b159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="registering-assemblies-with-com"></a><span data-ttu-id="a8af4-102">Registrieren von Assemblys mit COM</span><span class="sxs-lookup"><span data-stu-id="a8af4-102">Registering Assemblies with COM</span></span>
<span data-ttu-id="a8af4-103">Sie können ein Befehlszeilentool namens [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) ausführen, um eine Assembly für die Verwendung mit COM zu registrieren bzw. eine bestehende Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="a8af4-103">You can run a command-line tool called the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register or unregister an assembly for use with COM.</span></span> <span data-ttu-id="a8af4-104">Regasm.exe fügt der Systemregistrierung Informationen über die Klasse hinzu, damit COM-Clients die .NET Framework-Klasse transparent nutzen können.</span><span class="sxs-lookup"><span data-stu-id="a8af4-104">Regasm.exe adds information about the class to the system registry so COM clients can use the .NET Framework class transparently.</span></span> <span data-ttu-id="a8af4-105">Die Klasse <xref:System.Runtime.InteropServices.RegistrationServices> stellt gleichwertige Funktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="a8af4-105">The <xref:System.Runtime.InteropServices.RegistrationServices> class provides the equivalent functionality.</span></span>  
  
 <span data-ttu-id="a8af4-106">Eine verwaltete Komponente muss in der Windows-Registrierung registriert sein, damit sie von einem COM-Client aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8af4-106">A managed component must be registered in the Windows registry before it can be activated from a COM client.</span></span> <span data-ttu-id="a8af4-107">Die folgende Tabelle zeigt die Schlüssel, die Regasm.exe der Windows-Registrierung in der Regel hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="a8af4-107">The following table shows the keys that Regasm.exe typically adds to the Windows registry.</span></span> <span data-ttu-id="a8af4-108">(000000 steht hier für den tatsächlichen GUID-WERT.)</span><span class="sxs-lookup"><span data-stu-id="a8af4-108">(000000 indicates the actual GUID value.)</span></span>  
  
|<span data-ttu-id="a8af4-109">GUID</span><span class="sxs-lookup"><span data-stu-id="a8af4-109">GUID</span></span>|<span data-ttu-id="a8af4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8af4-110">Description</span></span>|<span data-ttu-id="a8af4-111">Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="a8af4-111">Registry key</span></span>|  
|----------|-----------------|------------------|  
|<span data-ttu-id="a8af4-112">CLSID</span><span class="sxs-lookup"><span data-stu-id="a8af4-112">CLSID</span></span>|<span data-ttu-id="a8af4-113">Klassen-ID</span><span class="sxs-lookup"><span data-stu-id="a8af4-113">Class identifier</span></span>|<span data-ttu-id="a8af4-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="a8af4-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span></span>|  
|<span data-ttu-id="a8af4-115">IID</span><span class="sxs-lookup"><span data-stu-id="a8af4-115">IID</span></span>|<span data-ttu-id="a8af4-116">Schnittstellen-ID</span><span class="sxs-lookup"><span data-stu-id="a8af4-116">Interface identifier</span></span>|<span data-ttu-id="a8af4-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="a8af4-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span></span>|  
|<span data-ttu-id="a8af4-118">LIBID</span><span class="sxs-lookup"><span data-stu-id="a8af4-118">LIBID</span></span>|<span data-ttu-id="a8af4-119">Bibliothek-ID</span><span class="sxs-lookup"><span data-stu-id="a8af4-119">Library identifier</span></span>|<span data-ttu-id="a8af4-120">HKEY_CLASSES_ROOT\TypeLib\\{000... 000}</span><span class="sxs-lookup"><span data-stu-id="a8af4-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span></span>|  
|<span data-ttu-id="a8af4-121">ProgID</span><span class="sxs-lookup"><span data-stu-id="a8af4-121">ProgID</span></span>|<span data-ttu-id="a8af4-122">Programmatischer Bezeichner</span><span class="sxs-lookup"><span data-stu-id="a8af4-122">Programmatic identifier</span></span>|<span data-ttu-id="a8af4-123">HKEY_CLASSES_ROOT\000... 000</span><span class="sxs-lookup"><span data-stu-id="a8af4-123">HKEY_CLASSES_ROOT\000…000</span></span>|  
  
 <span data-ttu-id="a8af4-124">Unter dem Schlüssel HKCR\CLSID\\{0000…0000} wird der Standardwert auf die ProgID der Klasse festgelegt, und zwei neue benannte Werte werden hinzugefügt, „Class“ und „Assembly“.</span><span class="sxs-lookup"><span data-stu-id="a8af4-124">Under the HKCR\CLSID\\{0000…0000} key, the default value is set to the ProgID of the class, and two new named values, Class and Assembly, are added.</span></span> <span data-ttu-id="a8af4-125">Die Common Language Runtime liest den Wert „Assembly“ aus der Registrierung aus und übergibt ihn an den Assemblyresolver der Runtime.</span><span class="sxs-lookup"><span data-stu-id="a8af4-125">The runtime reads the Assembly value from the registry and passes it on to the runtime assembly resolver.</span></span> <span data-ttu-id="a8af4-126">Der Assemblyresolver versucht, die Assembly anhand von Assemblyinformationen zu lokalisieren, z.B. Name und Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="a8af4-126">The assembly resolver attempts to locate the assembly, based on assembly information such as the name and version number.</span></span> <span data-ttu-id="a8af4-127">Damit der Assemblyresolver eine Assembly lokalisieren kann, muss sie sich an einem der folgenden Speicherorte befinden:</span><span class="sxs-lookup"><span data-stu-id="a8af4-127">For the assembly resolver to locate an assembly, the assembly has to be in one of the following locations:</span></span>  
  
-   <span data-ttu-id="a8af4-128">Im globalen Assemblycache (die Assembly muss einen starken Namen haben)</span><span class="sxs-lookup"><span data-stu-id="a8af4-128">The global assembly cache (must be a strong-named assembly).</span></span>  
  
-   <span data-ttu-id="a8af4-129">Im Anwendungsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a8af4-129">In the application directory.</span></span> <span data-ttu-id="a8af4-130">Auf aus einem Anwendungspfad geladene Assemblies kann nur über diese Anwendung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a8af4-130">Assemblies loaded from the application path are only accessible from that application.</span></span>  
  
-   <span data-ttu-id="a8af4-131">Entlang eines Dateipfads, der in Regasm.exe mit der Option **/codebase** angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a8af4-131">Along an file path specified with the **/codebase** option to Regasm.exe.</span></span>  
  
 <span data-ttu-id="a8af4-132">Regasm.exe erstellt auch unter dem Schlüssel HKCR\CLSID\\{0000…0000} den Schlüssel InProcServer32.</span><span class="sxs-lookup"><span data-stu-id="a8af4-132">Regasm.exe also creates the InProcServer32 key under the HKCR\CLSID\\{0000…0000} key.</span></span> <span data-ttu-id="a8af4-133">Als Standardwert für den Schlüssel ist der Name der DLL festgelegt, die die Common Language Runtime initialisiert (Mscoree.dll).</span><span class="sxs-lookup"><span data-stu-id="a8af4-133">The default value for the key is set to the name of the DLL that initializes the common language runtime (Mscoree.dll).</span></span>  
  
## <a name="examining-registry-entries"></a><span data-ttu-id="a8af4-134">Untersuchen von Registrierungseinträgen</span><span class="sxs-lookup"><span data-stu-id="a8af4-134">Examining Registry Entries</span></span>  
 <span data-ttu-id="a8af4-135">Das COM-Interop stellt eine standardmäßige Klassenfactoryimplementierung zum Erstellen einer Instanz einer beliebigen .NET Framework-Klasse bereit.</span><span class="sxs-lookup"><span data-stu-id="a8af4-135">COM interop provides a standard class factory implementation to create an instance of any .NET Framework class.</span></span> <span data-ttu-id="a8af4-136">Clients können für die verwaltete DLL **DllGetClassObject** aufrufen, um eine Klassenfactory zu erhalten und Objekte zu erstellen. Dies funktioniert genau wie bei jeder anderen COM-Komponente auch.</span><span class="sxs-lookup"><span data-stu-id="a8af4-136">Clients can call **DllGetClassObject** on the managed DLL to get a class factory and create objects, just as they would with any other COM component.</span></span>  
  
 <span data-ttu-id="a8af4-137">Für den Unterschlüssel `InprocServer32` wird statt einer traditionellen Bibliothek der COM-Typen ein Verweis auf die Datei „Mscoree.dll“ angezeigt. So wird angegeben, dass die Common Language Runtime das verwaltete Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8af4-137">For the `InprocServer32` subkey, a reference to Mscoree.dll appears in place of a traditional COM type library to indicate that the common language runtime creates the managed object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8af4-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8af4-138">See Also</span></span>  
 [<span data-ttu-id="a8af4-139">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="a8af4-139">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="a8af4-140">Gewusst wie: Verweisen auf .NET-Typen in COM</span><span class="sxs-lookup"><span data-stu-id="a8af4-140">How to: Reference .NET Types from COM</span></span>](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)  
 [<span data-ttu-id="a8af4-141">Aufrufen eines.</span><span class="sxs-lookup"><span data-stu-id="a8af4-141">Calling a .NET Object</span></span>](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [<span data-ttu-id="a8af4-142">Deploying an Application for COM Access (Bereitstellen einer Anwendung für COM-Zugriff)</span><span class="sxs-lookup"><span data-stu-id="a8af4-142">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
