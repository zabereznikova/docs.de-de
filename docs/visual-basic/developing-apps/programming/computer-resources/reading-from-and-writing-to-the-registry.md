---
title: Lesen von der und Schreiben in die Registrierung
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: bb400ef89edaa4eb743aee3a7f2cc5b9dfec4534
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360058"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="683fc-102">Lesen aus der und Schreiben in die Registrierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="683fc-102">Reading from and Writing to the Registry (Visual Basic)</span></span>

<span data-ttu-id="683fc-103">In diesem Thema werden die Aufgaben und konzeptionellen Themen beschrieben, die mit der Registrierung in Verbindung stehen.</span><span class="sxs-lookup"><span data-stu-id="683fc-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="683fc-104">Beim Programmieren in Visual Basic können Sie auf die Registrierung zugreifen. Dies geschieht entweder über die in Visual Basic bereitgestellten Funktionen oder die Registrierungsklassen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="683fc-104">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="683fc-105">Die Registrierung enthält Informationen des Betriebssystems und Informationen von auf dem Computer gehosteten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="683fc-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="683fc-106">Das Arbeiten mit der Registrierung schränkt möglicherweise die Sicherheit ein, da nicht ordnungsgemäßer Zugriff auf Systemressourcen oder geschützte Informationen zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="683fc-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="683fc-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="683fc-107">In This Section</span></span>  

 [<span data-ttu-id="683fc-108">Gewusst wie: Erstellen von Registrierungsschlüsseln und Festlegen ihrer Werte</span><span class="sxs-lookup"><span data-stu-id="683fc-108">How to: Create a Registry Key and Set Its Value</span></span>](how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="683fc-109">Beschreibt die Verwendung der Methoden `CreateSubKey` und `SetValue` des `My.Computer.Registry`-Objekts zum Erstellen eines Registrierungsschlüssels und das Festlegen seines Werts</span><span class="sxs-lookup"><span data-stu-id="683fc-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="683fc-110">Gewusst wie: Lesen eines Werts aus einem Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="683fc-110">How to: Read a Value from a Registry Key</span></span>](how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="683fc-111">Beschreibt die Verwendung der `GetValue`-Methode des `My.Computer.Registry`-Objekts zum Lesen eines Werts aus einem Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="683fc-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="683fc-112">Gewusst wie: Löschen von Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="683fc-112">How to: Delete a Registry Key</span></span>](how-to-delete-a-registry-key.md)  
 <span data-ttu-id="683fc-113">Beschreibt die Verwendung der `DeleteSubKey`-Methode der `My.Computer.Registry.CurrentUser`-Eigenschaft zum Löschen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="683fc-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="683fc-114">Lesen aus der und Schreiben in die Registrierung mithilfe des Namespaces „Microsoft.Win32“</span><span class="sxs-lookup"><span data-stu-id="683fc-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="683fc-115">Beschreibt die Verwendung der Klassen `Registry` und `RegistryKey` von .NET Framework für den Zugriff auf die Registrierung</span><span class="sxs-lookup"><span data-stu-id="683fc-115">Describes how to use the `Registry` and `RegistryKey` classes of the .NET Framework to access the registry.</span></span>  
  
 [<span data-ttu-id="683fc-116">Sicherheit und die Registrierung</span><span class="sxs-lookup"><span data-stu-id="683fc-116">Security and the Registry</span></span>](security-and-the-registry.md)  
 <span data-ttu-id="683fc-117">Beschreibt Sicherheitsprobleme im Zusammenhang mit der Registrierung</span><span class="sxs-lookup"><span data-stu-id="683fc-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="683fc-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="683fc-118">Related Sections</span></span>  

 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="683fc-119">Listet die Member des `My.Computer.Registry`-Objekts auf und erklärt diese</span><span class="sxs-lookup"><span data-stu-id="683fc-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="683fc-120">Bietet einen Überblick über die Klasse `Registry` und Links zu einzelnen Schlüsseln und Membern</span><span class="sxs-lookup"><span data-stu-id="683fc-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
