---
title: "Verwenden der switch-Aktivität mit benutzerdefinierten Typen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a4418c582d00f1163305ce5d63c63c198dbc30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a>Verwenden der switch-Aktivität mit benutzerdefinierten Typen
In diesem Beispiel enthält Informationen zum Aktivieren einer <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a `wechseln "Anweisung arbeitet mit einem Ausdruck, der statisch ausgewertet werden kann. In C# bedeutet dies z. B., dass nur primitive Typen wie <xref:System.Boolean>, <xref:System.Int32> oder <xref:System.String> und Enumerationstypen unterstützt werden.  
  
 Um die switch-Funktion für eine benutzerdefinierte Klasse zu aktivieren, muss Logik zur Auswertung des komplexen benutzerdefinierten Typs zur Laufzeit implementiert werden. In diesem Beispiel wird veranschaulicht, wie die switch-Funktion für einen benutzerdefinierten komplexen Typ mit dem Namen `Person` aktiviert wird.  
  
-   In der benutzerdefinierten Klasse `Person` wird ein <xref:System.ComponentModel.TypeConverter>-Attribut mit dem Namen des benutzerdefinierten <xref:System.ComponentModel.TypeConverter> deklariert.  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   In der benutzerdefinierten Klasse `Person` werden die <xref:System.Object.Equals%2A>-Klasse und die <xref:System.Object.GetHashCode%2A>-Klasse überschrieben.  
  
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
  
-   Eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter>-Klasse wird implementiert. Diese führt die Konvertierung einer Instanz der benutzerdefinierten Klasse in eine Zeichenfolge sowie die Konvertierung einer Zeichenfolge in eine Instanz der benutzerdefinierten Klasse aus.  
  
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
  
 Die folgenden Dateien sind in diesem Projekt enthalten:  
  
-   **Person.cs**: definiert die `Person` Klasse.  
  
-   **PersonConverter.cs**: der Typkonverter für das `Person` Klasse.  
  
-   **Sequence.XAML**: ein Workflow, über die `Person` Typ.  
  
-   **Datei "Program.cs"**: die main-Funktion, die der Workflow ausgeführt wird.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Laden Sie "Switch.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um das Beispiel auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a>Siehe auch  
 [Integrierte Aktivitätsbibliothek](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
