---
title: Verwenden der switch-Aktivität mit benutzerdefinierten Typen
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: 2b6f3109324064cb5e746de9c61e5a70c4c4d60b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517880"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="13ebb-102">Verwenden der switch-Aktivität mit benutzerdefinierten Typen</span><span class="sxs-lookup"><span data-stu-id="13ebb-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="13ebb-103">Dieses Beispiel zeigt, wie eine <xref:System.Activities.Statements.Switch%601>-Aktivität aktiviert wird, um zur Laufzeit einen benutzerdefinierten komplexen Typ auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="13ebb-103">This sample describes how to enable a <xref:System.Activities.Statements.Switch%601> activity to evaluate a user-defined complex type at runtime.</span></span> <span data-ttu-id="13ebb-104">In den meisten herkömmlichen prozeduralen Programmiersprachen wird eine [wechseln](http://go.microsoft.com/fwlink/?LinkId=180521) -Anweisung wählt eine Ausführungslogik basierend auf der bedingten Auswertung einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="13ebb-104">In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable.</span></span> <span data-ttu-id="13ebb-105">Normalerweise wird eine `switch`-Anweisung auf einen Ausdruck angewendet, der statisch ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="13ebb-105">Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="13ebb-106">In C# bedeutet dies z. B., dass nur primitive Typen wie <xref:System.Boolean>, <xref:System.Int32> oder <xref:System.String> und Enumerationstypen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="13ebb-106">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="13ebb-107">Um die switch-Funktion für eine benutzerdefinierte Klasse zu aktivieren, muss Logik zur Auswertung des komplexen benutzerdefinierten Typs zur Laufzeit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="13ebb-107">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="13ebb-108">In diesem Beispiel wird veranschaulicht, wie die switch-Funktion für einen benutzerdefinierten komplexen Typ mit dem Namen `Person` aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="13ebb-108">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="13ebb-109">In der benutzerdefinierten Klasse `Person` wird ein <xref:System.ComponentModel.TypeConverter>-Attribut mit dem Namen des benutzerdefinierten <xref:System.ComponentModel.TypeConverter> deklariert.</span><span class="sxs-lookup"><span data-stu-id="13ebb-109">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="13ebb-110">In der benutzerdefinierten Klasse `Person` werden die <xref:System.Object.Equals%2A>-Klasse und die <xref:System.Object.GetHashCode%2A>-Klasse überschrieben.</span><span class="sxs-lookup"><span data-stu-id="13ebb-110">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   <span data-ttu-id="13ebb-111">Eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter>-Klasse wird implementiert. Diese führt die Konvertierung einer Instanz der benutzerdefinierten Klasse in eine Zeichenfolge sowie die Konvertierung einer Zeichenfolge in eine Instanz der benutzerdefinierten Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="13ebb-111">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 <span data-ttu-id="13ebb-112">Die folgenden Dateien sind in diesem Projekt enthalten:</span><span class="sxs-lookup"><span data-stu-id="13ebb-112">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="13ebb-113">**Person.cs**: definiert die `Person` Klasse.</span><span class="sxs-lookup"><span data-stu-id="13ebb-113">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="13ebb-114">**PersonConverter.cs**: der Typkonverter für das `Person` Klasse.</span><span class="sxs-lookup"><span data-stu-id="13ebb-114">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="13ebb-115">**Sequence.XAML**: ein Workflow, über die `Person` Typ.</span><span class="sxs-lookup"><span data-stu-id="13ebb-115">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="13ebb-116">**Datei "Program.cs"**: die main-Funktion, die der Workflow ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="13ebb-116">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="13ebb-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="13ebb-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="13ebb-118">Laden Sie "Switch.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13ebb-118">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="13ebb-119">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="13ebb-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="13ebb-120">Drücken Sie STRG+F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="13ebb-120">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13ebb-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="13ebb-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="13ebb-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="13ebb-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="13ebb-123">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="13ebb-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13ebb-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="13ebb-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="13ebb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13ebb-125">See Also</span></span>  
 [<span data-ttu-id="13ebb-126">Integrierte Aktivitätsbibliothek</span><span class="sxs-lookup"><span data-stu-id="13ebb-126">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
