---
title: "Como acessar argumentos de linha de comando usando foreach (Guia de Programação em C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
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
ms.openlocfilehash: 766b5cd0879edec1dc409e07c4f62ee693fd615d
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Como acessar argumentos de linha de comando usando foreach (Guia de Programação em C#)
Outra abordagem para iterar na matriz é usar a instrução [foreach](../../../csharp/language-reference/keywords/foreach-in.md), conforme mostrado neste exemplo. A instrução `foreach` pode ser usada para iterar em uma matriz, em uma classe de coleção do .NET Framework ou em qualquer classe ou struct que implementa a interface <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  Ao executar um aplicativo no Visual Studio, você pode especificar argumentos de linha de comando na [Página de depuração, Designer de Projeto](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Exemplo  
 Este exemplo demonstra como imprimir os argumentos de linha de comando usando `foreach`.  
  
 [!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Array>   
 <xref:System.Collections>   
 [Compilação de linha de comando com csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Main() e argumentos de linha de comando](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Como exibir argumentos de linha de comando](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Valores de retorno de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

