---
title: Aktivitätslokalisierung
ms.date: 03/30/2017
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
ms.openlocfilehash: 23a6d5c2ed202f030397eb70382896468a68a724
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512462"
---
# <a name="activity-localization"></a><span data-ttu-id="4d0d1-102">Aktivitätslokalisierung</span><span class="sxs-lookup"><span data-stu-id="4d0d1-102">Activity Localization</span></span>
<span data-ttu-id="4d0d1-103">Wenn Workflowanwendungen und -Komponenten in andere Kulturen und Sprachen lokalisiert werden können, sollten Ressourcenzeichenfolgen verwendet werden, damit nach der Lokalisierung keine erneute Kompilierung ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-103">When workflow applications and components have the potential to be localized into other cultures and languages, resource strings should be used so that they can be localized without recompiling.</span></span>  
  
## <a name="activity-localization"></a><span data-ttu-id="4d0d1-104">Aktivitätslokalisierung</span><span class="sxs-lookup"><span data-stu-id="4d0d1-104">Activity Localization</span></span>  
 <span data-ttu-id="4d0d1-105">Wie bei allen Anwendungen, die lokalisiert (in verschiedenen Versionen für andere Sprachen und Kulturen veröffentlicht) werden müssen, sollten sämtliche Zeichenfolgen, die dem Benutzer angezeigt werden, nicht direkt in den Code aufgenommen, sondern stattdessen in einer Ressourcendatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-105">As with all applications that must be localized (released in different versions for different languages and cultures), any strings that are displayed to the user should not be put directly in code, but rather stored in a resource file.</span></span> <span data-ttu-id="4d0d1-106">Die Zeichenfolgen können dann über zugegriffen werden <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-106">The strings can then be accessed through <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span></span> <span data-ttu-id="4d0d1-107">Wenn Sie eine Komponente entwickeln, die in mehreren Sprachen herausgegeben wird, sollten Sie für Aktivitätsvalidierungsmeldungen, benutzerdefinierte Überwachungsdaten, Ablaufverfolgungsmeldungen und Fehlermeldungen ebenfalls Ressourcenzeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-107">If you are developing a component that is distributed in several languages, you also want to use resource strings for activity validation messages, user-defined tracking data, tracing messages, and error messages as well.</span></span>  
  
 <span data-ttu-id="4d0d1-108">Die folgende Übung demonstriert, wie eine Ressourcendatei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-108">The following exercise demonstrates how to use a resource file.</span></span>  
  
#### <a name="using-resource-files-for-localized-strings"></a><span data-ttu-id="4d0d1-109">Verwenden von Ressourcendateien für lokalisierte Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4d0d1-109">Using resource files for localized strings</span></span>  
  
1.  <span data-ttu-id="4d0d1-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], mit der rechten Maustaste des Projekts in **Projektmappen-Explorer** , und wählen Sie **hinzufügen...** , **Neues Element...** .</span><span class="sxs-lookup"><span data-stu-id="4d0d1-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], right-click your project in **Solution Explorer** and select **Add…**, **New Item…**.</span></span>  
  
2.  <span data-ttu-id="4d0d1-111">Wählen Sie **Ressourcendatei** und nennen Sie die Datei den Namen ErrorResources.resx.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-111">Select **Resources File** and name the file ErrorResources.resx.</span></span> <span data-ttu-id="4d0d1-112">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-112">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="4d0d1-113">Öffnen Sie die Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-113">Open the resource file.</span></span> <span data-ttu-id="4d0d1-114">Fügen Sie einen neuen Eintrag mit einer **Namen** ErrorString und ein **Wert** von "ist die Aktivität nicht gültig."</span><span class="sxs-lookup"><span data-stu-id="4d0d1-114">Add a new entry with a **Name** of ErrorString and a **Value** of "The activity is not valid."</span></span>  
  
4.  <span data-ttu-id="4d0d1-115">Fügen Sie der Klasse die folgenden `using`-Anweisungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-115">Add the following `using` statements to your class.</span></span>  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  <span data-ttu-id="4d0d1-116">Erstellen Sie einen Ressourcen-Manager in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-116">Create a resource manager in your project.</span></span>  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  <span data-ttu-id="4d0d1-117">Rufen Sie die Zeichenfolge aus dem Ressourcen-Manager dahin ab, wo es erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-117">Get the string from the resource manager where it is required.</span></span>  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 <span data-ttu-id="4d0d1-118">Im folgenden Codebeispiel wird veranschaulicht, wie lokalisierte Zeichenfolgen in der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d0d1-118">The following code sample demonstrates how to utilize localized strings in the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span>  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
