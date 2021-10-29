## snabbdom 学习

```
function patch(oldVnode: VNode | Element, vnode: VNode) {
  // ...省略
  if (sameVnode(oldVnode, vnode)) {
    patchVnode(oldVnode, vnode, insertedVnodeQueue);
  } else {
    elm = oldVnode.elm!;
    parent = api.parentNode(elm) as Node;

    createElm(vnode, insertedVnodeQueue);

    if (parent !== null) {
      api.insertBefore(parent, vnode.elm!, api.nextSibling(elm));
      removeVnodes(parent, [oldVnode], 0, 0);
    }
  }
  // ...省略
  return vnode
}

```
