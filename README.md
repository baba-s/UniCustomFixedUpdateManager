# UniCustomFixedUpdateManager

MonoBehaviour の FixedUpdate 関数の呼び出しを高速にするための機能

## 使用例

```cs
using Kogane;
using UnityEngine;

public class Example : MonoBehaviour, IFixedUpdatable
{
    private void OnEnable()
    {
        // コンポーネントが有効になったらマネージャに登録
        CustomFixedUpdateManager.Add( this );
    }

    private void OnDisable()
    {
        // コンポーネントが無効になったらマネージャから解除
        CustomFixedUpdateManager.Remove( this );
    }

    // MonoBehaviour.FixedUpdate の代わりに定義
    void IFixedUpdatable.OnFixedUpdate()
    {
        Debug.Log( "ピカチュウ" );
    }
}
```

## 参考

* https://www.packtpub.com/game-development/unity-2017-game-optimization-second-edition
* https://blogs.unity3d.com/jp/2015/12/23/1k-update-calls/
