# RECYCLEVIEW-ANDROID
Tutorial para implementar o RecycleView em um projeto Android

![alt tag](https://developer.android.com/training/material/images/RecyclerView.png)

- Links sobre RecycleView:

    - https://developer.android.com/training/material/lists-cards.html
    - https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html
    - https://developer.android.com/reference/android/support/v7/widget/RecyclerView.LayoutManager.html
    - https://developer.android.com/reference/android/support/v7/widget/LinearLayoutManager.html
    - https://developer.android.com/reference/android/support/v7/widget/RecyclerView.Adapter.html
    - https://developer.android.com/reference/android/support/v7/widget/RecyclerView.ViewHolder.html

- Passos para implementar o RecycleView:

1) Defini o RecicleView no seu layout.xml:
    <RecicleView
        android:id="@+id/rv"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
    />

2) Fazer refencia do objeto RecicleView em sua activity:
    private RecicleView rv;

    onCreate(..){
        rv = (RecicleView) findViewById(R.id.rv);
    }

3) Definir um LayoutManager para o RecicleView, vamos usar o LinearLayoutManager:
    private RecicleView rv;
    private LinearLayoutManager llm;

    onCreate(..){
        rv = (RecicleView) findViewById(R.id.rv);

        llm = new LinearLayoutManager(this);
        rv.setLayoutManager(llm)
    }

4) Como fizemos com o LayoutManager, precisamos de um adapter e definir para o RecicleView utilizar esse adapter, vamos criar um adapter customizado, para isso vamos criar uma class que 'extends' da class RecicleView.Adapter<>, porem, essa class necessita de um objeto do tipo Holder: