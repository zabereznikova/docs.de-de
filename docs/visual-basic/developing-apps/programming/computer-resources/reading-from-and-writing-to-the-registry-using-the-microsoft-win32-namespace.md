---
title: Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32-Namespaces
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 10431b1ad40ed320541a22fb46cc8db6dbb775b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360071"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="48441-102">Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48441-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>

<span data-ttu-id="48441-103">Mit `My.Computer.Registry` sollten zwar Ihre gesamten grundlegenden Anforderungen beim Programmieren der Registrierung abgedeckt werden, aber Sie können alternativ die Klassen <xref:Microsoft.Win32.Registry> und <xref:Microsoft.Win32.RegistryKey> im <xref:Microsoft.Win32>-Namespace von .NET Framework verwenden.</span><span class="sxs-lookup"><span data-stu-id="48441-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the .NET Framework.</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="48441-104">Schlüssel in der Registry-Klasse</span><span class="sxs-lookup"><span data-stu-id="48441-104">Keys in the Registry Class</span></span>  

 <span data-ttu-id="48441-105">Die <xref:Microsoft.Win32.Registry>-Klasse stellt die Basisregistrierungsschlüssel bereit, die für den Zugriff auf Unterschlüssel und deren Werte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="48441-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="48441-106">Die Basisschlüssel selbst sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="48441-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="48441-107">In der folgenden Tabelle werden die sieben Schlüssel, die von der <xref:Microsoft.Win32.Registry>-Klasse verfügbar gemacht werden, aufgelistet und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48441-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="48441-108">**Key**</span><span class="sxs-lookup"><span data-stu-id="48441-108">**Key**</span></span>|<span data-ttu-id="48441-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48441-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="48441-110">Definiert die Typen von Dokumenten und die diesen Typen zugeordneten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="48441-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="48441-111">Enthält Informationen zur Hardwarekonfiguration, die nicht spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="48441-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="48441-112">Enthält Informationen über die aktuellen Benutzereinstellungen, z.B. Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="48441-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="48441-113">Enthält dynamische Registrierungsdaten, z.B. solche, die von virtuellen Gerätetreibern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48441-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="48441-114">Enthält fünf Unterschlüssel (Hardware, SAM, Security, Software und System), die die Konfigurationsdaten für den lokalen Computer enthalten.</span><span class="sxs-lookup"><span data-stu-id="48441-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="48441-115">Enthält Informationen zur Leistung für Softwarekomponenten.</span><span class="sxs-lookup"><span data-stu-id="48441-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="48441-116">Enthält Informationen zu den Standardeinstellungen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="48441-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
> <span data-ttu-id="48441-117">Es ist sicherer, Daten in den Schlüssel für den aktuellen Benutzer (<xref:Microsoft.Win32.Registry.CurrentUser>) statt in den Schlüssel für den lokalen Computer (<xref:Microsoft.Win32.Registry.LocalMachine>) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="48441-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="48441-118">Eine Bedingung, die in der Regel als „squatting“ bezeichnet wird, tritt auf, wenn der Schlüssel, den Sie erstellen, zuvor von einem anderen, möglicherweise böswilligen Prozess erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="48441-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="48441-119">Um dies zu vermeiden, verwenden Sie eine Methode, z.B. <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, die `Nothing` zurückgibt, wenn der Schlüssel nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="48441-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="48441-120">Lesen eines Werts aus der Registrierung</span><span class="sxs-lookup"><span data-stu-id="48441-120">Reading a Value from the Registry</span></span>  

 <span data-ttu-id="48441-121">Der folgende Code zeigt, wie eine Zeichenfolge aus HKEY_CURRENT_USER gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="48441-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 <span data-ttu-id="48441-122">Der folgende Code liest, erhöht, und schreibt dann eine Zeichenfolge in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="48441-122">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="48441-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48441-123">See also</span></span>

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="48441-124">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="48441-124">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="48441-125">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="48441-125">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="48441-126">Sicherheit und die Registrierung</span><span class="sxs-lookup"><span data-stu-id="48441-126">Security and the Registry</span></span>](security-and-the-registry.md)
