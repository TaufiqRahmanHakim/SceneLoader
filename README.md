# SceneLoader

```csharp
using System.Collections;
using UnityEngine;
using UnityEngine.SceneManagement;

public class SceneLoader : MonoBehaviour
{
    [SerializeField] private Animator anim;

    public int sceneInt;

    public void TransitionScene(int wait)
    {
        StartCoroutine(SceneLevelLogic(wait));
    }

    IEnumerator SceneLevelLogic(int wait)
    {
        anim.SetTrigger("Start");
        yield return new WaitForSeconds(wait);
        SceneManager.LoadScene(sceneInt);
    }
}
```
