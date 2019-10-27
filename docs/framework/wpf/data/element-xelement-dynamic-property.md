---
title: 元素（XElement 动态属性）
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921184"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="9b40a-102">元素（XElement 动态属性）</span><span class="sxs-lookup"><span data-stu-id="9b40a-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="9b40a-103">获取一个索引器，用于检索与指定扩展名对应的子元素实例。</span><span class="sxs-lookup"><span data-stu-id="9b40a-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b40a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b40a-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="9b40a-105">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="9b40a-105">Property value/return value</span></span>

<span data-ttu-id="9b40a-106">一个类型为 `XElement Item(String expandedName)` 的索引器。</span><span class="sxs-lookup"><span data-stu-id="9b40a-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="9b40a-107">此索引器获取扩展名参数并返回相应的 <xref:System.Xml.Linq.XElement>，或者如果没有具有指定名称的元素，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="9b40a-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b40a-108">备注</span><span class="sxs-lookup"><span data-stu-id="9b40a-108">Remarks</span></span>

<span data-ttu-id="9b40a-109">此属性等效于 <xref:System.Xml.Linq.XContainer.Element%2A> 类的 <xref:System.Xml.Linq.XContainer?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="9b40a-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b40a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b40a-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="9b40a-111">XElement 类动态属性</span><span class="sxs-lookup"><span data-stu-id="9b40a-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="9b40a-112">元素</span><span class="sxs-lookup"><span data-stu-id="9b40a-112">Elements</span></span>](elements-xelement-dynamic-property.md)