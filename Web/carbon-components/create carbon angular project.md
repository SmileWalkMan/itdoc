## >ng new <projectname>
## >npm i --save carbon-components-angular carbon-components @carbon/icons-angular

### Then we need to include carbon-components in src/styles.scss:

@import "~carbon-components/scss/globals/scss/styles.scss";

## app.module.ts
import { AccordionModule, BreadcrumbModule, ButtonModule, } from 'carbon-components-angular';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,ButtonModule,
  ],
  providers: [],
  bootstrap: [AppComponent]
})

##
1. html直接添加：<button ibmButton="primary" size="normal">Button2</button>

2. ts添加属性
export class AppComponent {
  title = 'bidi-rtlcss';
  ibmButton: string;
	size: string;
	ngOnInit(): void {
		this.ibmButton = "primary";
		this.size = "normal";
	}
}
html直接添加：
<button [ibmButton]="ibmButton" [size]="size">Button</button>