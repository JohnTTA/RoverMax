
public class Rover {
	private static String[] pos=new String[]{"n", "e", "s", "w"};
	private int x, y;
	private int look;
	public Rover(int x, int y, String look) {
		this.x=x;
		this.y=y;
		switch(look) {
			case "n": this.look=0; break;
			case "e": this.look=1; break;
			case "s": this.look=2; break;
			case "w": this.look=3; break;
		}
	}
	public void move() {
		switch(pos[look]) {
			case "e": x++; break;
			case "w": x--; break;
			case "n": y++; break;
			case "s": y--; break;
			default: break;
		}
	}
	public void rotate(String turn) {
		switch(turn) {
		case "l": look--; break;
		case "r": look++; break;
		}
	}
	public String getOrientation() {
		if(look<pos.length) {look=pos.length-1;}
		if(look>pos.length-1) {look=0;}
		return pos[look];
	}
}
