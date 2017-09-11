---
title: "Gewusst wie: Erstellen eines Schlüssels in der Registrierung (Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96d34df3314494fc96ad8b55d7462b67dcc7bd72
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="2dc25-102">Gewusst wie: Erstellen eines Schlüssels in der Registrierung (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="2dc25-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="2dc25-103">Dieses Beispiel fügt der Registrierung des aktuellen Benutzers unter dem Schlüssel "Names" das Wertepaar "Name" und "Isabella" hinzu.</span><span class="sxs-lookup"><span data-stu-id="2dc25-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dc25-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2dc25-104">Example</span></span>  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2dc25-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2dc25-105">Compiling the Code</span></span>  
  
-   <span data-ttu-id="2dc25-106">Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="2dc25-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
-   <span data-ttu-id="2dc25-107">Ersetzen Sie den `Names`-Parameter durch den Namen eines Schlüssels, der sich in der Registrierung direkt unter dem HKEY_CURRENT_USER-Knoten befindet.</span><span class="sxs-lookup"><span data-stu-id="2dc25-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
-   <span data-ttu-id="2dc25-108">Ersetzen Sie den `Name`-Parameter durch den Namen eines Werts, der sich direkt unterhalb des Names-Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="2dc25-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2dc25-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="2dc25-109">Robust Programming</span></span>  
 <span data-ttu-id="2dc25-110">Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2dc25-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="2dc25-111">Sie können beispielsweise den Schlüssel Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="2dc25-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="2dc25-112">Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.</span><span class="sxs-lookup"><span data-stu-id="2dc25-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="2dc25-113">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="2dc25-113">The following conditions might cause an exception:</span></span>  
  
-   <span data-ttu-id="2dc25-114">Der Name des Schlüssels ist NULL.</span><span class="sxs-lookup"><span data-stu-id="2dc25-114">The name of the key is null.</span></span>  
  
-   <span data-ttu-id="2dc25-115">Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt.</span><span class="sxs-lookup"><span data-stu-id="2dc25-115">The user does not have permissions to create registry keys.</span></span>  
  
-   <span data-ttu-id="2dc25-116">Der Name des Schlüssels ist länger als 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2dc25-116">The key name exceeds the 255-character limit.</span></span>  
  
-   <span data-ttu-id="2dc25-117">Der Schlüssel ist geschlossen.</span><span class="sxs-lookup"><span data-stu-id="2dc25-117">The key is closed.</span></span>  
  
-   <span data-ttu-id="2dc25-118">Der Registrierungsschlüssel ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2dc25-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2dc25-119">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2dc25-119">.NET Framework Security</span></span>  
 <span data-ttu-id="2dc25-120">Es ist sicherer, die Daten in den Benutzerordner (`Microsoft.Win32.Registry.CurrentUser`) anstatt auf den lokalen Computer (`Microsoft.Win32.Registry.LocalMachine`) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="2dc25-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="2dc25-121">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2dc25-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="2dc25-122">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="2dc25-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="2dc25-123">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2dc25-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="2dc25-124">Um dies zu verhindern, verwenden Sie die `Overload:Microsoft.Win32.RegistryKey.GetValue`-</span><span class="sxs-lookup"><span data-stu-id="2dc25-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="2dc25-125">-Methode.</span><span class="sxs-lookup"><span data-stu-id="2dc25-125">method.</span></span> <span data-ttu-id="2dc25-126">Die Methode gibt NULL zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2dc25-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="2dc25-127">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="2dc25-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc25-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dc25-128">See Also</span></span>  
 <span data-ttu-id="2dc25-129"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2dc25-129"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="2dc25-130">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2dc25-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2dc25-131">[Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md) </span><span class="sxs-lookup"><span data-stu-id="2dc25-131">[File System and the Registry (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md) </span></span>  
 [<span data-ttu-id="2dc25-132">Read, write and delete from the registry with C# (Ausführen von Aktionen in der Registrierung mit C#: Lesen, Schreiben und Löschen)</span><span class="sxs-lookup"><span data-stu-id="2dc25-132">Read, write and delete from the registry with C#</span></span>](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)

